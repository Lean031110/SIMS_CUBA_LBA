# Análisis de Android como plataforma objetivo

La grabación del 26-11-2026 muestra CubitaLife funcionando en Chrome móvil en Android, con un diseño vertical y un teléfono virtual que agrupa muchos subsistemas. Esto demuestra que existe una experiencia web móvil utilizable durante esa sesión; **no demuestra la existencia de una app Android nativa** ni sustituye las pruebas en dispositivos distintos.

## Observaciones útiles para nuestra app
- La navegación móvil tiene alta densidad funcional: launcher en cuadrícula, buscador de módulos, dock y accesos rápidos.
- Las pantallas de negocio, vivienda, mercado y sociales requieren paneles largos y scroll vertical.
- El mundo aparece en vista isométrica con mapa, lugares seleccionables y personajes.
- Los datos del HUD (necesidades, cartera, reputación, estado y misiones) deben permanecer legibles sin tapar el mundo.
- El diseño Android propio debe priorizar controles táctiles y navegación de una mano; no trasladar el flujo desktop del cursor a una WebView.
- Las pantallas deben adaptar escala, safe areas, orientación y densidad.

## Requisitos propios
- Instalación APK para QA y AAB cuando se decida distribución.
- Controles touch-first, cámara por gestos y alternativa accesible a joystick.
- Soporte para múltiples relaciones de aspecto, pantallas pequeñas y tablets.
- Pausa/reanudación y reconexión tras suspensión del proceso.
- Gestión de memoria, batería, temperatura, almacenamiento y datos móviles.
- Permisos mínimos y privacidad.
- Pruebas en teléfono real, no solo emulador.

## Pendiente
Definir versión mínima de Android, RAM/GPU objetivo, tamaño APK, FPS target, resolución, política de orientación y requisitos offline mediante benchmark de una primera escena original.
