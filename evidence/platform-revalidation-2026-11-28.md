# Revalidación de plataforma y backend — 28-11-2026

**Tipo:** investigación documental; no se ejecutó una build, benchmark ni despliegue.
**Objetivo:** comprobar si las decisiones provisionales de Android y realtime siguen siendo válidas y ajustar los gates antes del vertical slice.

## 1. Hallazgo principal: Godot 4.8 llegó a RC, pero no es estable

### Estados de versión
- **DOCUMENTED — confianza alta:** el archivo oficial de Godot muestra Godot 4.7.2 como estable (18-08-2026) y Godot 4.8 RC 1 publicado el 27-11-2026 como pre-release.
- **DOCUMENTED — confianza alta:** el anuncio oficial de RC 1 dice que los bloqueos críticos conocidos están resueltos y que las funciones previstas quedaron congeladas, pero pide pruebas comunitarias extensas. No equivale a una versión estable.
- **DOCUMENTED — confianza alta:** la documentación estable de exportación Android continúa enumerando JDK 17, Platform 35, Build-Tools 35.0.1, NDK r28b y CMake 3.10.2.4988404.
- **DOCUMENTED — confianza alta, con caveat de versión:** la documentación latest se identifica expresamente como inestable. Describe una configuración automática de SDK/Java a partir de Godot 4.8 y recomienda JDK 17, Platform 36, Build-Tools 36.1.0, NDK 29.0.14206865 y CMake 3.22.1. No asumir que cada detalle de latest está garantizado en la plantilla exacta de RC 1.
- **DOCUMENTED — confianza alta:** Google Play exige API 36 o superior para nuevas apps y actualizaciones desde el 31-08-2026.

### Consecuencia
El gate anterior no debe limitarse a probar 4.7.2 con API 36. Ahora conviene una comparación controlada:
1. Godot 4.7.2 estable + ruta documentada estable, investigando de forma separada cómo fijar targetSdkVersion=36 sin alterar silenciosamente la plantilla.
2. Godot 4.8 RC 1 + toolchain API 36 descrito por la documentación latest, verificando qué está realmente incluido en el RC.
3. Mismo proyecto mínimo, mismo dispositivo, mismo perfil de exportación y mismo smoke test.

No elegir 4.8 RC 1 para producción solo porque la documentación más nueva menciona API 36. La decisión sigue PENDING hasta que exista una versión estable compatible y una build comprobada. Si RC 1 es la única ruta técnicamente viable, esperar a la versión estable o documentar explícitamente el riesgo de pre-release antes de aprobar.

### Gate de exportación
- Registrar versión exacta del editor y hash/versión de plantillas.
- Registrar versiones de JDK, Android CLI/SDK, Platform, Build-Tools, NDK y CMake.
- Exportar APK debug; inspeccionar el manifiesto final y comprobar targetSdkVersion=36.
- Instalar y abrir en Android 16 real y en un Android anterior que se decida como dispositivo de compatibilidad.
- Verificar permisos, orientación, safe areas, audio, pausa/reanudación y arranque en frío.
- Guardar logs, checksum, dispositivo, sistema operativo y resultado. No subir keystores ni credenciales.
- Comparar tamaño, FPS, RAM, temperatura, batería y fallos con una escena de prueba idéntica.

**No realizado:** no se instaló Godot, no se exportó APK, no se inspeccionó manifiesto y no se probó teléfono en esta revisión.

## 2. Backend realtime: detalles que cambian el spike

### Cloudflare Durable Objects
- **DOCUMENTED — confianza alta:** en Workers Free, DO SQLite dispone de 100.000 requests/día y 13.000 GB-s/día de duración. La cuota de almacenamiento SQLite Free documentada es 5 millones de filas leídas/día, 100.000 escritas/día y 5 GB totales.
- **DOCUMENTED — confianza alta:** las requests incluyen HTTP, sesiones RPC, mensajes WebSocket y alarmas. Cada conexión WebSocket requiere una request; los mensajes entrantes se facturan con una relación 20:1 para el cómputo de requests; los mensajes salientes y pings de protocolo no generan ese cargo de request.
- **DOCUMENTED — confianza alta:** Hibernation reduce cargos de duración cuando el objeto puede hibernar, pero no elimina requests, almacenamiento, ejecución activa ni límites. I/O pendiente puede mantener un objeto activo hasta 15 minutos.
- **DOCUMENTED — confianza alta:** al superar una cuota Free, las operaciones de ese tipo fallan hasta el reinicio diario en UTC. No es capacidad garantizada para producción.

Implicación: el spike debe contabilizar conexiones, mensajes entrantes, escrituras, lecturas, duración activa y operaciones del Worker de entrada por separado. Medir un único contador de usuarios conectados no basta.

### Vercel
- **DOCUMENTED — confianza alta:** WebSockets en Vercel Functions pasó a disponibilidad general el 20-10-2026.
- **DOCUMENTED — confianza alta:** con Fluid Compute, el máximo de duración de Function es 300 s en Hobby, 800 s en Pro/Enterprise y 1.800 s como máximo extendido beta en Pro/Enterprise.
- **HYPOTHESIS — confianza media:** puede servir para sesiones cortas, lobby o chat con reconexión, pero no debe asumirse que una Function sea un proceso de mundo persistente indefinido. El diseño debe recuperar estado desde almacenamiento externo y probar explícitamente la desconexión.

### Supabase Realtime
- **DOCUMENTED — confianza alta:** la tabla oficial consultada mantiene Free en 200 conexiones concurrentes y 100 mensajes por segundo; la página fue actualizada el 29-10-2026.
- **DOCUMENTED — confianza alta:** sigue siendo un candidato para auth/SQL/presencia/chat auxiliar, no autoridad automática para economía, inventario o simulación. Las cuotas y la política de pausa del proyecto Free deben considerarse.

## 3. SDKs de servidor de juego

### Colyseus + Godot
- **DOCUMENTED — confianza alta:** la documentación v0.18 lista Android entre las plataformas del SDK Godot.
- **DOCUMENTED — confianza alta:** la misma página advierte que el GDExtension está en beta y puede no ser estable; el Native SDK compartido sigue en desarrollo y puede introducir breaking changes.
- **PENDING:** compatibilidad exacta con Godot 4.7.2 y 4.8 RC 1, exportación Android arm64, reconexión, consumo y estabilidad bajo carga.

No tratar la existencia de un SDK Godot como prueba de integración lista para producción.

### Nakama + Godot 4
- **DOCUMENTED — confianza alta:** Heroic Labs mantiene una guía de cliente Godot 4 que documenta cliente, socket realtime y matches server-authoritative/server-relayed.
- **DOCUMENTED — confianza alta:** el modo server-authoritative mantiene la lógica de match en el servidor; el modo relayed deja el control en clientes y no debe usarse como autoridad para economía o progreso.
- **PENDING:** versión exacta del SDK, compatibilidad con la versión de Godot seleccionada, exportación Android, tamaño, latencia y recursos del servidor.

## 4. Diseño del spike backend

Se añade docs/04-technical-architecture/backend-spike-plan.md. Comparará:
1. Worker + Durable Object por zona.
2. Colyseus en servidor propio.
3. Nakama en servidor propio.

Usará clientes sintéticos, una zona de prueba y estado no económico. Se medirán 20/50/100 clientes, mensajes, bytes, CPU/RAM, latencia p50/p95, reconexión, recuperación de snapshot, consistencia y coste. Las tasas propuestas son perfiles de estrés, no requisitos finales del juego. No se abrirá chat público ni se probará dinero real.

## 5. Evidencia de CubitaLife y bloqueos

- **PENDING:** no se obtuvo una sesión autenticada nueva en esta revisión. No se accedió a la cuenta ni se usaron credenciales.
- La grabación del 26-11 sigue confirmando pantallas y textos; no prueba efectos de acciones, persistencia, movimiento real ni fórmulas.
- El vacío de mayor impacto sigue siendo onboarding → personaje → primer spawn → movimiento/cámara → selección de edificio → interior/salida.
- El siguiente material útil es el clip B del plan de captura, seguido del clip A si puede observarse el primer flujo sin resetear la cuenta.

## 6. Fuentes consultadas el 28-11-2026

| Fuente | Publicación/actualización | Uso | Confianza |
|---|---|---|---|
| https://godotengine.org/download/archive/ | Archivo vivo; consultado 28-11-2026 | 4.7.2 estable y 4.8 RC 1 pre-release | Alta |
| https://godotengine.org/article/release-candidate-godot-4-8-rc-1/ | 27-11-2026 | Estado y advertencia de RC | Alta |
| https://docs.godotengine.org/en/latest/tutorials/export/exporting_for_android.html | latest inestable; consultado 28-11-2026 | Toolchain API 36 y setup desde 4.8 | Alta para lo que documenta; no prueba RC exacto |
| https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_android.html | Documentación estable; consultado 28-11-2026 | Toolchain estable listado para exportación | Alta |
| https://support.google.com/googleplay/android-developer/answer/11926878?hl=en-en | Requisito desde 31-08-2026; consultado 28-11-2026 | Target API 36 | Alta |
| https://developers.cloudflare.com/durable-objects/platform/pricing/ | Actualizado 13-11-2026; consultado 28-11-2026 | Cuotas, facturación de WebSocket y Hibernation | Alta |
| https://vercel.com/changelog/websocket-support-is-now-generally-available | 20-10-2026; consultado 28-11-2026 | WebSockets GA | Alta |
| https://vercel.com/docs/functions/limitations | Página viva; consultado 28-11-2026 | Máxima duración por plan | Alta |
| https://supabase.com/docs/guides/realtime/limits | Actualizado 29-10-2026; consultado 28-11-2026 | Cuotas Realtime Free | Alta |
| https://docs.colyseus.io/getting-started/godot | Docs v0.18; consultado 28-11-2026 | SDK Godot beta y plataformas | Alta |
| https://heroiclabs.com/docs/nakama/client-libraries/godot/ | Guía Godot 4; consultado 28-11-2026 | Cliente/socket y multiplayer | Alta |

## Conclusión
La investigación no justifica cambiar ya de motor ni de backend. Sí justifica ampliar el gate Android para comparar 4.7.2 estable y 4.8 RC 1, y rebajar el nivel de confianza operativo del SDK Godot de Colyseus hasta probarlo. No iniciar implementación grande ni aprobar proveedor por esta evidencia documental.
