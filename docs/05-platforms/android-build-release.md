# Android build y release

## Herramientas
Fijar versión exacta de Godot 4.x estable, Android SDK, platform-tools, build-tools, JDK y plantilla de exportación. Registrar versiones en el repositorio al crear el proyecto.

## Flujo
1. Ejecutar tests headless y análisis de scripts.
2. Exportar APK debug para QA interna.
3. Instalar por ADB en dispositivos físicos y registrar modelo/Android/ABI.
4. Ejecutar smoke tests de login demo, mundo, controles, pausa/reanudación y red.
5. Perfilar memoria, FPS, carga, temperatura, batería y fallos.
6. Release: firmar AAB/APK con credenciales fuera de Git; nunca subir keystore o passwords.
7. Guardar checksum, versión, commit, notas y resultados de QA.

## Compatibilidad
Probar Android mínimo después de medir; cubrir ARM64, densidades y relaciones de aspecto. Diseñar recuperación para caída de conectividad, pero no permitir acciones económicas no confirmadas.

No existe build ni APK actual; esta guía define el futuro pipeline.