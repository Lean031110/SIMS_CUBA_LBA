# Estado actual del proyecto

**Corte:** 27-11-2026  
**Fase:** 0 — investigación y preproducción  
**Implementación:** no iniciada  
**Plataforma principal:** Android instalable (APK para QA; AAB para Google Play cuando corresponda).

## Estado del repositorio
- Rama principal: `main`, último commit revisado: `de5cd1022183e0c3d5c30368d29e9d9e6dafb7c7` (26-11-2026, análisis de términos/monetización).
- PR #4 `research/cubitalife-session-audit-2026-11-26` sigue abierto, sin merge, con 17 archivos modificados; es mergeable según la lectura de GitHub al 27-11-2026.
- Este trabajo se desarrolla en una rama apilada sobre la rama del PR #4 para conservar su evidencia; no se modifica `main`.
- El árbol de la rama de auditoría contiene 88 entradas; el árbol de `main`, 86 entradas en la revisión actual.
- No hay implementación jugable, APK, backend ni despliegue.

## Qué está confirmado
- La portada pública reconsultada el 27-11-2026 sigue mostrando HUD de ejemplo, cuatro necesidades, navegación Explorar/Trabajo/Estudiar/Mi casa/Viajar por Cuba, escena de La Habana, chat y controles de cámara.
- Los términos oficiales consultados el 27-11-2026 indican última actualización 12-11-2026; declaran 18+, reglas de cuenta/dispositivo, monedas ficticias, diamantes, Stripe, reembolsos, datos y anuncios.
- La grabación aportada por el propietario el 26-11-2026 muestra una sesión autenticada en Chrome/Android: mapa isométrico de Camagüey, avatar/otros jugadores, HUD, teléfono virtual y pantallas de múltiples subsistemas.
- La sesión permite confirmar pantallas y textos, no operaciones económicas o sociales completadas.

## Qué sigue pendiente
- Registro/login real, validaciones, recuperación y primera creación de personaje.
- Primer spawn, tutorial, condiciones iniciales y variación entre cuentas.
- Movimiento táctil, rotación/zoom efectivos, colisiones, selección de lugares y entrada/salida de edificios.
- Cambios temporales de necesidades, wallet, misiones y persistencia.
- Efectos completos de empleo, cursos, vivienda, comercio, viajes y salud.
- Privacidad, ajustes, bloqueo/reporte, chat y mensajes privados.
- App Android nativa: la grabación demuestra Chrome móvil, no una app nativa.
- Motor, backend, base de datos, APIs y protocolo privados de CubitaLife siguen desconocidos.

## Investigación técnica revalidada
- Godot 4.7.2 es la versión estable publicada más reciente consultada; Godot 4.8 está en beta5 al 24-11-2026.
- Godot 4.7 documenta JDK 17 y un conjunto de herramientas Android basado en SDK 35; Google Play exige target API 36 para nuevas apps/actualizaciones desde 31-08-2026. La combinación exacta debe probarse.
- Vercel WebSockets pasó a GA el 20-10-2026, pero cada conexión depende de la duración máxima de Function y del estado externo.
- Cloudflare Workers/DO, Supabase, Render y Fly.io tienen cuotas, límites o gasto potencial; ninguno se considera producción gratuita ilimitada.

## Bloqueos
1. No hay una sesión autenticada del propietario disponible para esta ejecución; no se accedió a la cuenta ni se usaron credenciales. La grabación anterior cubre solo un recorrido de pantallas.
2. La evidencia de onboarding, spawn y controles requiere una captura nueva y redactada del propietario.
3. No se ha hecho benchmark en teléfono Android real ni prueba de carga del backend.
4. Edad, licencia, marca, privacidad, moderación y monetización propias siguen pendientes de aprobación.

## Próximos hitos
1. Completar el plan de captura de onboarding, spawn, movimiento, cámara y transiciones.
2. Completar observaciones no destructivas de HUD/necesidades, ajustes y privacidad.
3. Cerrar matriz de paridad v1 y GDD, separando observación y propuesta.
4. Probar exportación Godot estable con target API 36 y perfilar dispositivo real.
5. Ejecutar spike de backend con carga, reconexión, costes y latencia de regiones objetivo.
6. Solo después, iniciar el vertical slice original.
