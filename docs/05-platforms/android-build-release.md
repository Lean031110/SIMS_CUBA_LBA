# Android build y release — revisión 28-11-2026

## Estado
No existe build ni APK. La elección del motor y el toolchain permanece PENDING hasta completar la comparación API 36 en hardware real.

## Requisito de distribución
Google Play exige target API 36 o superior para nuevas aplicaciones y actualizaciones desde el 31-08-2026. Target API no es lo mismo que minSdk: el primero define el comportamiento esperado frente a Android moderno; el segundo determina el Android mínimo compatible.

## Versiones y toolchain documentado
| Línea | Estado | JDK | Platform | Build-Tools | NDK | CMake | Interpretación |
|---|---|---:|---:|---:|---|---|---|
| Godot 4.7.2 | Estable | 17 recomendado | 35 | 35.0.1 | r28b / 28.1.13356709 | 3.10.2.4988404 | Guía estable; target 36 no demostrado |
| Godot 4.8 RC 1 | Pre-release, publicado 27-11-2026 | 17 recomendado | 36 | 36.1.0 | 29.0.14206865 | 3.22.1 | La guía latest/inestable describe esta línea desde 4.8; validar contra el RC exacto |

La documentación latest avisa que puede describir funciones no disponibles o incompatibles con versiones estables. No copiar su toolchain a Godot 4.7.2 sin prueba.

## Gate A — Godot 4.7.2 estable
1. Instalar Godot 4.7.2 y export templates exactos.
2. Preparar JDK 17 y paquetes de la guía estable.
3. Añadir Platform 36/Build-Tools 36.1.0 únicamente para investigar el target requerido; documentar cualquier Gradle personalizado.
4. Exportar APK debug.
5. Inspeccionar el manifiesto final y comprobar targetSdkVersion 36.
6. Registrar errores y modificaciones; no ocultar parches locales.

## Gate B — Godot 4.8 RC 1
1. Instalar RC 1 en entorno separado.
2. Registrar hash de editor y export templates.
3. Probar el setup automático del editor o el toolchain manual documentado para API 36.
4. Exportar APK debug y verificar manifiesto.
5. Registrar incompatibilidades de plugins, extensiones y scripts.
6. Mantenerlo como experimento pre-release; no usarlo para producción sin versión estable y repetición completa del gate.

## Gate común de dispositivo
- Instalar en Android 16 real y un Android anterior elegido como mínimo de compatibilidad.
- Smoke test: arranque frío, navegación, orientación, safe areas, audio, permisos, pausa/reanudación, pérdida/restablecimiento de red.
- Medir FPS, RAM, temperatura, batería, tamaño de APK, tiempo de carga y cierres.
- Repetir en un dispositivo modesto y uno medio antes de fijar requisitos mínimos.
- Guardar logs, checksum, modelo, versión Android, ABI, versiones del toolchain y resultado.

## Seguridad de release
- APK debug para QA interna.
- AAB cuando se apruebe distribución.
- Firmar con credenciales fuera de Git; nunca subir keystore, passwords ni tokens.
- Asociar cada artefacto a commit, versión, checksum y resultados de QA.

## Fuentes oficiales
- https://godotengine.org/download/archive/
- https://godotengine.org/article/release-candidate-godot-4-8-rc-1/
- https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_android.html
- https://docs.godotengine.org/en/latest/tutorials/export/exporting_for_android.html
- https://support.google.com/googleplay/android-developer/answer/11926878?hl=en-en

Ver [revalidación de plataforma 28-11](../../evidence/platform-revalidation-2026-11-28.md). No se ha ejecutado ninguna build.
