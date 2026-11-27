# Android build y release — revisión 27-11-2026

## Versiones candidatas
- Godot 4.7.2 estable (publicado 18-08-2026).
- Godot 4.8 beta 5 (24-11-2026) solo para comparación experimental; no fijar beta para producción.
- OpenJDK 17 recomendado por la guía estable.

## Toolchain documentado por versión
| Fuente | Platform | Build-Tools | NDK | CMake | Estado |
|---|---:|---:|---|---|---|
| Godot stable Android export | 35 | 35.0.1 | r28b / 28.1.13356709 | 3.10.2.4988404 | Guía estable consultada |
| Godot latest/4.8 docs | 36 | 36.1.0 | 29.0.14206865 | 3.22.1 | Documentación latest/unstable |

La guía estable enumera Platform 35, pero Google Play exige target API 36 para nuevas apps y actualizaciones desde el 31-08-2026. La combinación exacta de plantilla Godot 4.7.2 y target 36 queda PENDING hasta probarla.

## Gate de exportación
1. Instalar Godot 4.7.2 estable, JDK 17 y paquetes de la guía estable.
2. Mantener Android Platform 36 y Build-Tools 36.1.0 disponibles para la prueba.
3. Crear un proyecto mínimo y exportar APK debug con target API 36.
4. Si la plantilla precompilada no permite el target requerido, probar Gradle build personalizado según documentación oficial.
5. Inspeccionar el manifiesto del APK y confirmar targetSdkVersion 36.
6. Instalar en Android 16 real y ejecutar smoke test; probar también un Android anterior.
7. Repetir como comparación con Godot 4.8 beta 5, dejando explícito que es pre-release.
8. Guardar versiones, logs, checksum y resultado en el repositorio.

## Flujo futuro
1. Ejecutar tests headless y análisis de scripts.
2. Exportar APK debug para QA interna.
3. Instalar por ADB en dispositivos físicos y registrar modelo/Android/ABI.
4. Ejecutar smoke tests de cuenta demo, mundo, controles, pausa/reanudación y red.
5. Perfilar memoria, FPS, carga, temperatura, batería y fallos.
6. Release: firmar AAB/APK con credenciales fuera de Git; nunca subir keystore o passwords.
7. Guardar checksum, versión, commit, notas y resultados de QA.

## Compatibilidad
Probar Android mínimo después de medir; cubrir ARM64, densidades y relaciones de aspecto. Diseñar recuperación para caída de conectividad, pero no permitir acciones económicas no confirmadas.

No existe build ni APK actual; esta guía define el futuro pipeline.
