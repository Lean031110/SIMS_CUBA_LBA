# ADR-001 — Motor del cliente Android

- Estado: **Godot 4.7.2 estable como baseline de comparación; Godot 4.8 RC 1 como candidato experimental. Decisión final PENDING.**
- Revisión: 28-11-2026.
- Lenguaje propuesto: GDScript.

## Contexto
El producto es 3D y Android-first. Se necesita un cliente instalable, rendimiento razonable en hardware modesto, tooling reproducible y compatibilidad con target API 36 para distribución futura en Google Play.

## Evidencia de versión y toolchain
- **DOCUMENTED — alta:** Godot 4.7.2 figura como estable en el archivo oficial.
- **DOCUMENTED — alta:** Godot 4.8 RC 1 se publicó el 27-11-2026 y sigue siendo pre-release. El anuncio dice que se han resuelto los bloqueos críticos conocidos, pero solicita pruebas comunitarias extensas.
- **DOCUMENTED — alta:** la guía estable Android enumera OpenJDK 17, Android Platform 35, Build-Tools 35.0.1, NDK r28b (28.1.13356709) y CMake 3.10.2.4988404.
- **DOCUMENTED — alta:** la guía latest se identifica expresamente como inestable y documenta desde Godot 4.8 setup automático y Platform 36, Build-Tools 36.1.0, NDK 29.0.14206865 y CMake 3.22.1.
- **DOCUMENTED — alta:** Google Play exige target API 36 o superior para nuevas apps y actualizaciones desde 31-08-2026.
- **PENDING:** la plantilla exacta de Godot 4.7.2 con target API 36.
- **PENDING:** que Godot 4.8 RC 1 exporte y ejecute de forma estable en los dispositivos objetivo; la guía latest no garantiza por sí sola la plantilla RC exacta.

Fuentes:
- https://godotengine.org/download/archive/
- https://godotengine.org/article/release-candidate-godot-4-8-rc-1/
- https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_android.html
- https://docs.godotengine.org/en/latest/tutorials/export/exporting_for_android.html
- https://support.google.com/googleplay/android-developer/answer/11926878?hl=en-en

## Candidatos
### Godot 4.7.2 estable
Ventajas: rama estable y soporte de mantenimiento. Su guía estable, sin embargo, enumera Platform 35, por debajo del target API 36 requerido por Google Play para nuevas publicaciones. Debe probarse si puede exportar target 36 con un flujo compatible y reproducible.

### Godot 4.8 RC 1
Ventajas: línea próxima a estable y documentación latest con setup API 36. Riesgos: sigue siendo pre-release; la documentación latest puede adelantarse a la plantilla exacta del RC y los plugins pueden no estar listos.

### Alternativas
- Unity: ecosistema móvil amplio; revisar condiciones comerciales y requisitos vigentes.
- Unreal: capacidad visual alta, pero riesgo de rendimiento/tamaño en dispositivos modestos.
- Three.js/Babylon + Capacitor: útil para web-first, pero un wrapper no equivale a cliente nativo.
- LibGDX/Defold: alternativas ligeras; comparar 3D, UI, tooling y flujo Android.

## Gate de decisión
1. Preparar un proyecto mínimo idéntico en 4.7.2 estable y 4.8 RC 1.
2. Registrar editor, export templates, JDK, SDK Platform, Build-Tools, NDK y CMake exactos.
3. Exportar APK debug con target API 36. Si 4.7.2 requiere Gradle personalizado, documentar cada modificación y comprobar que no altera otros requisitos.
4. Inspeccionar manifiesto final y confirmar targetSdkVersion=36; no inferirlo por el preset.
5. Instalar/ejecutar en Android 16 real y un Android anterior.
6. Probar permisos, orientación, safe areas, pausa/reanudación, arranque en frío y conectividad.
7. Comparar tamaño APK, FPS, RAM, temperatura, batería y estabilidad con la misma escena.
8. Revisar compatibilidad de plugins/GDExtensions usados.
9. Mantener RC como experimento hasta que exista versión estable y se repita el gate.

**No realizado:** no se instaló motor, no se exportó APK, no se inspeccionó manifiesto ni se probó hardware. La decisión no está aprobada.

## Consecuencias previstas si se aprueba
Escenas/nodos y GDScript; separar mundo, UI, cámara, avatar, dominio y red; backend por HTTPS/WebSocket; recursos y shaders optimizados. Fijar versión exacta en el repositorio solo después del gate.
