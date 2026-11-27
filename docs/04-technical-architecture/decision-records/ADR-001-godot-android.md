# ADR-001 — Motor del cliente Android

- Estado: **candidato recomendado para prototipo; aprobación bloqueada por compatibilidad API 36 y benchmark real**.
- Revisión: 27-11-2026.
- Propuesta provisional: Godot 4.7.2 estable + GDScript, cliente Android instalable.

## Contexto
El producto es 3D y Android-first. El equipo necesita iterar con agentes, controlar tamaño y rendimiento en dispositivos modestos y evitar una WebView como sustituto de app nativa.

## Evidencia de versión
- **CONFIRMED:** Godot 4.7.2 figura como estable; lanzamiento de mantenimiento 18-08-2026.
- **DOCUMENTED:** Godot 4.8 beta 5 salió el 24-11-2026, pero es pre-release. No se adopta como base estable.
- **DOCUMENTED:** la guía estable de exportación Android enumera JDK 17, Android Platform 35, Build-Tools 35.0.1, NDK r28b y CMake 3.10.2.4988404.
- **DOCUMENTED:** Google Play requiere target API 36 para nuevas apps y actualizaciones desde 31-08-2026.
- **PENDING:** compatibilidad exacta de la plantilla 4.7.2 con target API 36.
- **DOCUMENTED, pre-release:** la guía latest/unstable de Godot ya describe setup automático desde 4.8 y paquetes Platform 36 / Build-Tools 36.1.0 / NDK 29 / CMake 3.22.1. No asumir que ese toolchain es intercambiable con 4.7.2.

Fuentes:
- https://godotengine.org/article/maintenance-release-godot-4-7-2/
- https://godotengine.org/download/archive/
- https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_android.html
- https://docs.godotengine.org/en/latest/tutorials/export/exporting_for_android.html
- https://developer.android.com/google/play/requirements/target-sdk

## Motivos para mantener Godot como candidato
- Motor open source y orientado a proyectos 2D/3D.
- GDScript reduce fricción de tooling y permite mantener el código principal en un lenguaje accesible al equipo.
- Exportación Android documentada y flujo de APK para QA.
- Arquitectura de nodos/escenas adecuada para separar mundo, UI, cámara, personaje y sistemas de dominio.
- Evita convertir la app principal en una WebView.

## Alternativas
- Unity: ecosistema móvil amplio; revisar condiciones comerciales y requisitos de build vigentes.
- Unreal: alta capacidad visual, pero riesgo de coste de rendimiento/tamaño en dispositivos modestos.
- Three.js/Babylon + Capacitor: útil para una experiencia web-first, pero un wrapper no equivale a cliente nativo.
- LibGDX/Defold: alternativas ligeras; requieren comparar tooling, 3D, UI y flujo Android.

## Gate de aprobación
1. Proyecto vacío en Godot 4.7.2 estable.
2. Exportar APK debug con target API 36 y verificar el manifiesto.
3. Instalar/ejecutar en Android 16 y en un dispositivo Android anterior.
4. Crear escena original con personaje, cámara, terreno y UI táctil.
5. Medir FPS, RAM, tamaño APK, carga, temperatura, batería, controles y estabilidad de red.
6. Repetir medición en un dispositivo modesto y uno medio.
7. Comparar con 4.8 beta 5 únicamente como referencia experimental.

La decisión no se considera aprobada hasta superar este gate. No hay aún build ni APK.

## Consecuencias previstas si se aprueba
Escenas/nodos y GDScript; backend separado por HTTPS/WebSocket; activos y shaders optimizados para Android; web opcional futura. La versión exacta del motor y del SDK quedará fijada en el repositorio cuando el gate se complete.
