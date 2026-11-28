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

## Revalidación de toolchain — 27-11-2026

### Versiones del motor
- **CONFIRMED:** Godot 4.7.2 figura como versión estable y fue publicada el 18-08-2026.
- **DOCUMENTED:** Godot 4.8 beta 5 fue publicada el 24-11-2026. Sigue siendo una versión pre-release; no se debe fijar como base de producción mientras no sea estable.
- **DOCUMENTED:** la documentación estable de exportación Android recomienda OpenJDK 17, Android Platform 35, Build-Tools 35.0.1, NDK r28b (28.1.13356709) y CMake 3.10.2.4988404.
- **DOCUMENTED:** la documentación latest/unstable, que ya refleja cambios de Godot 4.8, muestra setup automático y un toolchain diferente: Platform 36, Build-Tools 36.1.0, NDK 29.0.14206865 y CMake 3.22.1.

### Requisito Google Play
- **DOCUMENTED:** desde el 31-08-2026, nuevas aplicaciones y actualizaciones enviadas a Google Play deben targetear Android 16 / API 36 o superior.
- **PENDING:** no se ha demostrado que la plantilla estable de Godot 4.7.2 exporte correctamente un APK con target API 36. La guía estable consultada todavía enumera Platform 35; la guía latest de 4.8 no puede tratarse como prueba para 4.7.2.
- **Riesgo:** el motor estable recomendado y el requisito de publicación pueden necesitar una configuración Gradle/plantilla específica. No asumir compatibilidad por el mero hecho de instalar Android SDK 36.

### Gate técnico obligatorio
Antes de fijar la versión del motor:
1. Crear un proyecto Godot vacío en 4.7.2 estable.
2. Instalar JDK 17 y los paquetes Android que exige la guía estable; mantener también Platform 36 y Build-Tools 36.1.0 disponibles para la prueba.
3. Exportar APK debug con target API 36 usando la plantilla oficial. Si no es posible, probar la ruta Gradle personalizada documentada por Godot y registrar todos los cambios.
4. Inspeccionar el manifiesto final para confirmar targetSdkVersion 36; no basta con que el proyecto compile.
5. Instalar y ejecutar en un Android 16 real y en al menos un Android anterior compatible.
6. Repetir como comparación con Godot 4.8 beta 5, pero no promover beta a estable por ganar la prueba.
7. Registrar versiones exactas, logs, tamaño, ABI, errores y checksum.

## Pendiente de dispositivo
Definir versión mínima de Android, RAM/GPU objetivo, tamaño APK, FPS target, resolución, política de orientación y requisitos offline mediante benchmark de una primera escena original en un teléfono real.


## Revalidación del toolchain — 28-11-2026
- **DOCUMENTED:** Godot 4.8 RC 1 fue publicado el 27-11-2026 y sigue marcado pre-release; 4.7.2 continúa como estable en el archivo oficial.
- **DOCUMENTED:** la guía estable de exportación sigue listando Platform 35 / Build-Tools 35.0.1 / NDK r28b / CMake 3.10.2.4988404.
- **DOCUMENTED:** la guía latest, explícitamente inestable, documenta desde Godot 4.8 setup automático y Platform 36 / Build-Tools 36.1.0 / NDK 29 / CMake 3.22.1.
- **DOCUMENTED:** Google Play exige target API 36 desde el 31-08-2026.
- **PROPOSAL:** comparar 4.7.2 estable y 4.8 RC 1 con el mismo proyecto mínimo, verificar targetSdkVersion en el APK e instalar en Android 16 y un Android anterior. No adoptar RC para producción sin versión estable y pruebas.
- **PENDING:** no se ha instalado/exportado nada ni probado un dispositivo en esta revisión.

Ver [revalidación de plataforma](../../evidence/platform-revalidation-2026-11-28.md) y [ADR-001](../04-technical-architecture/decision-records/ADR-001-godot-android.md).
