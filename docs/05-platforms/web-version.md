# Cliente web — opción futura

Android es la plataforma principal. Una versión web puede evaluarse después si el backend y el modelo de identidad están estabilizados.

## Uso potencial
Web pública, launcher ligero, panel de comunidad o cliente secundario. No asumir que una build web sustituye al rendimiento ni a la experiencia táctil nativa.

## Riesgos
GPU/memoria de navegador, restricciones de WebGL/WebAssembly, sockets, compatibilidad móvil y tamaño de assets. La exportación web debe perfilarse separadamente.

## Regla
No retrasar el cliente Android para construir web. Compartir lógica de dominio y APIs donde sea razonable; no forzar una base UI común si perjudica rendimiento o UX.