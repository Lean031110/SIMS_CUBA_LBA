# ADR-001 — Motor del cliente Android

- Estado: recomendado para prototipo; validación pendiente.
- Fecha: 26-11-2026.
- Propuesta: Godot 4.x estable + GDScript, cliente Android nativo.

## Contexto
El producto es 3D y Android-first. El equipo necesita iterar con agentes, controlar tamaño y rendimiento en dispositivos modestos y evitar una WebView como sustituto de app nativa.

## Motivos
- Godot documenta exportación Android: https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_android.html
- Su documentación de Web export advierte de limitaciones específicas y menor rendimiento frente a builds móviles nativas: https://docs.godotengine.org/en/latest/tutorials/export/exporting_for_web.html
- GDScript reduce fricción de tooling y evita depender de rutas C# con limitaciones de plataforma.
- Godot es open source; revisar la licencia exacta y dependencias al crear el proyecto.

## Alternativas
- Unity: ecosistema amplio; verificar términos comerciales vigentes.
- Unreal: gran capacidad visual, pero más pesado para equipo pequeño y gama media/baja.
- Three.js/Babylon + Capacitor: atractivo para web-first, pero wrapper no garantiza experiencia nativa.

## Riesgos y pruebas
Crear escena de prueba y medir FPS, memoria, tamaño APK, carga, temperatura, batería, controles y animaciones en al menos un dispositivo bajo y uno medio. La decisión solo queda aprobada tras ese benchmark.

## Consecuencias
Escenas/nodos y GDScript; backend separado por HTTPS/WebSocket; activos y shaders optimizados para Android; web opcional futura.
