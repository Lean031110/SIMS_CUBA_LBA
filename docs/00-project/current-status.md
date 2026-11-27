# Estado actual del proyecto

**Corte:** 27-11-2026  
**Fase:** 0 — investigación y preproducción  
**Implementación:** no iniciada  
**Plataforma principal:** Android instalable (APK para QA; AAB cuando corresponda a distribución).

## Estado del repositorio
- Rama principal: main; último commit revisado en main: de5cd1022183e0c3d5c30368d29e9d9e6dafb7c7.
- PR #4 (auditoría visual de sesión) continúa abierto y sin merge.
- Rama de esta revisión: research/2026-11-27-evidence-and-platform-revalidation, apilada sobre la rama del PR #4 para evitar duplicar su diff.
- Los cambios de esta revisión son documentales; no se modificó main.
- No hay implementación jugable, APK, backend ni despliegue.

## Qué está confirmado
- La portada oficial se reconsultó el 27-11-2026 y sigue mostrando formulario de cuenta, HUD de ejemplo, cuatro necesidades, navegación principal, escena de La Habana, chat y controles de cámara.
- Los términos oficiales se reconsultaron el 27-11-2026 y mantienen como fecha de última actualización el 12-11-2026. Sus afirmaciones son DOCUMENTED, no pruebas de transacciones.
- La grabación aportada por el propietario el 26-11-2026 muestra una sesión autenticada en Chrome/Android: mapa isométrico de Camagüey, avatar/otros jugadores, HUD, teléfono virtual y pantallas de múltiples subsistemas.
- La sesión confirma pantallas y textos; no demuestra operaciones económicas/sociales, fórmulas, persistencia ni sincronización.

## Qué sigue pendiente en CubitaLife
- Registro/login real, validaciones, recuperación y primera creación de personaje.
- Primer spawn, tutorial, estado inicial y variación entre cuentas.
- Movimiento táctil, rotación/zoom efectivos, colisiones, selección de lugares y entrada/salida de edificios.
- Cambios temporales de necesidades, wallet, misiones y persistencia.
- Efectos completos de empleo, cursos, vivienda, comercio, viajes y salud.
- Privacidad, ajustes, bloqueo/reporte, chat y mensajes privados.
- La grabación demuestra Chrome móvil; no demuestra una aplicación Android nativa.
- Motor, backend, base de datos, APIs y protocolo privados de CubitaLife siguen desconocidos.

## Investigación técnica revalidada el 27-11-2026
- Godot 4.7.2 es estable; Godot 4.8 beta 5 (24-11-2026) es pre-release.
- La guía estable de Godot Android enumera JDK 17, Platform 35, Build-Tools 35.0.1, NDK r28b y CMake 3.10.2.4988404.
- Google Play exige target API 36 desde el 31-08-2026. La compatibilidad de la plantilla Godot 4.7.2 con target 36 sigue PENDING y bloquea fijar el toolchain.
- La guía latest/unstable de Godot 4.8 muestra un toolchain Android más nuevo; no se asume compatible con 4.7.2.
- Cloudflare Workers/DO ofrece cuotas Free medibles, pero al exceder límites algunas operaciones fallan; Hibernation reduce duración facturable, no hace el tráfico ilimitado.
- Vercel WebSockets es GA desde 20-10-2026, pero las Functions tienen duración máxima (Hobby 300 s).
- Supabase Realtime Free limita a 200 conexiones y 100 mensajes/s; proyectos con poca actividad pueden pausarse tras 7 días.
- Firebase Spark ofrece 100 conexiones simultáneas en Realtime Database; Blaze factura uso adicional.
- Render Free duerme tras 15 min, su filesystem es efímero y Postgres Free expira a 30 días.
- Fly.io es de pago por uso; Colyseus y Nakama son alternativas self-hosted que requieren servidor y operación.
- Ningún tier gratuito se considera producción 24/7 ni ilimitada.

## Bloqueos
1. No hay una sesión autenticada del propietario disponible para esta ejecución; no se accedió a la cuenta ni se utilizaron credenciales. La grabación previa cubre solo pantallas.
2. La evidencia de onboarding, spawn y controles requiere una captura nueva, legítima y redactada del propietario.
3. No se ha hecho benchmark Android real ni prueba de carga del backend.
4. La compatibilidad Godot 4.7.2 / target API 36 debe demostrarse con un APK y su manifiesto.
5. Edad, licencia, marca, privacidad, moderación y monetización propias siguen pendientes de aprobación.

## Próximos hitos
1. Completar el plan de captura de onboarding, spawn, movimiento, cámara y transiciones.
2. Completar observaciones no destructivas de HUD/necesidades, ajustes y privacidad.
3. Cerrar matriz de paridad v1 y GDD sin convertir UI en comportamiento no probado.
4. Probar exportación Godot estable con target API 36 y perfilar dispositivo real.
5. Comparar Cloudflare DO con Colyseus/Nakama mediante prueba de carga, reconexión, coste y latencia desde redes objetivo.
6. Solo después de superar los gates, iniciar el vertical slice original.
