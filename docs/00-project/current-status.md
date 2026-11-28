# Estado actual del proyecto

**Corte:** 28-11-2026  
**Fase:** 0 — investigación y preproducción  
**Implementación:** no iniciada  
**Plataforma principal:** Android instalable (APK para QA; AAB cuando corresponda a distribución).

## Estado del repositorio
- Rama principal: main; último commit revisado en main: de5cd1022183e0c3d5c30368d29e9d9e6dafb7c7.
- PR #4 (auditoría visual de sesión) sigue abierto y sin merge.
- PR #5 (revalidación Android API 36 y backend realtime) sigue abierto y apilado sobre la rama del PR #4.
- PR #6 (Godot 4.8 RC / API 36 y spike backend) está abierto, apilado sobre la rama del PR #5.
- Rama de esta revisión: research/2026-11-28-godot-48-android-spike.
- No se modificó main. Los cambios de esta revisión son documentales.
- Árbol de la rama revisado: 91 entradas, sin truncamiento.
- No hay implementación jugable, APK, backend ni despliegue.

## Qué está confirmado de CubitaLife
- La portada pública muestra registro/login, HUD de ejemplo, cuatro necesidades, navegación principal, escena de La Habana, chat y controles de cámara.
- Los términos públicos declaran edad mínima 18+, reglas de cuenta/dispositivo, monedas ficticias, diamantes, pagos y tratamiento de datos.
- La grabación aportada el 26-11-2026 muestra una sesión autenticada en Chrome/Android: mapa isométrico de Camagüey, avatar/otros jugadores, HUD, teléfono virtual y pantallas de múltiples subsistemas.
- La sesión confirma pantallas y textos; no demuestra operaciones económicas/sociales, fórmulas, persistencia ni sincronización.
- No se obtuvo una nueva sesión interactiva en la revisión del 28-11. No se accedió a la cuenta ni se utilizaron credenciales.

## Qué sigue pendiente en CubitaLife
- Registro/login real, validaciones, recuperación y primera creación de personaje.
- Primer spawn, tutorial, estado inicial y variación entre cuentas.
- Movimiento táctil, rotación/zoom efectivos, colisiones, selección de lugares y entrada/salida de edificios.
- Cambios temporales de necesidades, wallet, misiones y persistencia.
- Efectos completos de empleo, cursos, vivienda, comercio, viajes y salud.
- Privacidad, ajustes, bloqueo/reporte, chat y mensajes privados.
- La grabación demuestra Chrome móvil; no demuestra una aplicación Android nativa.
- Motor, backend, base de datos, APIs y protocolo privados de CubitaLife siguen desconocidos.

## Investigación técnica revalidada — 28-11-2026
- Godot 4.7.2 continúa como versión estable identificada en el archivo oficial.
- Godot 4.8 RC 1 se publicó el 27-11-2026 y sigue siendo pre-release.
- La guía estable Android lista JDK 17, Platform 35, Build-Tools 35.0.1, NDK r28b y CMake 3.10.2.4988404.
- La guía latest, declarada inestable, documenta desde 4.8 setup automático y Platform 36, Build-Tools 36.1.0, NDK 29 y CMake 3.22.1.
- Google Play exige target API 36 para nuevas apps y actualizaciones desde 31-08-2026. La compatibilidad de 4.7.2/4.8 RC 1 con el target requerido debe probarse; no hay APK.
- Cloudflare Workers/DO mantiene cuotas Free finitas. En DO, requests, duración y almacenamiento tienen límites distintos; Hibernation no elimina todos los cargos.
- Vercel WebSockets es GA desde 20-10-2026, pero las Functions siguen sujetas a duración máxima.
- Supabase Realtime Free documenta 200 conexiones y 100 mensajes/s; los proyectos Free pueden pausarse por inactividad.
- Colyseus lista Android, pero su GDExtension Godot está en beta. Nakama dispone de guía de cliente Godot 4 con sockets y matches server-authoritative.
- Se añadió un protocolo de spike para comparar Cloudflare DO, Colyseus y Nakama; no se ejecutó.

## Bloqueos
1. No hay nueva sesión autenticada autorizada disponible; onboarding, spawn y controles requieren captura legítima del propietario.
2. La compatibilidad Godot 4.7.2 y 4.8 RC 1 con target API 36 debe demostrarse con APK y manifiesto.
3. No se ha probado Android real ni medido FPS, RAM, temperatura, batería o compatibilidad.
4. No se ha ejecutado prueba de carga, reconexión, restore ni latencia desde redes cubanas.
5. Edad, licencia, marca, privacidad, moderación y monetización propias siguen pendientes de aprobación.

## Próximos hitos
1. Completar clip B del plan de captura: movimiento, cámara, edificio e interior/salida; después clip A si el onboarding se puede observar sin resetear cuenta.
2. Completar observaciones no destructivas de HUD, ajustes, privacidad y social.
3. Cerrar matriz de paridad v1 y GDD sin convertir UI en comportamiento no probado.
4. Comparar Godot 4.7.2 estable y 4.8 RC 1 con target API 36; inspeccionar manifiestos y probar dispositivos reales.
5. Ejecutar el spike de backend con perfiles sintéticos, reconexión, restauración y coste.
6. Solo después de superar los gates, iniciar el vertical slice original.
