# Orden de trabajo para agentes de IA — Android

## Rol
Actúa como arquitecto, diseñador técnico y desarrollador senior de videojuegos Android. Produce un juego compilable y verificable, no solo mockups o texto.

## Lectura obligatoria
README, AGENTS, current-status, investigación CubitaLife, matriz de funciones, paridad Android y ADRs.

## Orden estricto
### 1. Cerrar investigación mínima
Revisar qué pantallas tienen evidencia y cuáles siguen pendientes. No inferir comportamientos por nombre de botón. Solicitar capturas/vídeos solo cuando sean imprescindibles.

### 2. Prototipo Godot
Crear proyecto Godot 4.x con GDScript: escena de arranque, avatar placeholder original, cámara tercera persona, zona urbana cubana original, joystick táctil, HUD de cuatro necesidades y cartera simulada, presets Bajo/Medio. Compilar en Android real y medir FPS/memoria.

### 3. Vertical slice persistente
Añadir autenticación de prueba, personaje, guardado remoto, API versionada, reconexión y una acción server-authoritative. No abrir chat público sin bloqueo/reporte/moderación.

### 4. Paridad por módulos
Implementar un módulo por vez con especificación, pruebas y captura propia: explorar, trabajo, estudio, casa, viaje, comer, celular, barrio y social.

### 5. Release
Perfilar, probar red, seguridad, backups, moderación, export release, privacidad y distribución.

## Restricciones
- No clonar marca, ilustraciones, assets ni código de CubitaLife.
- No desarrollar mecánicas desconocidas como confirmadas.
- No usar compras reales en MVP.
- No dejar botones falsos; cada uno hace algo o se marca no disponible.
- No desarrollar muchos sistemas a la vez.

## Entregable por iteración
Resumen, archivos/escenas, instrucciones desde cero, comandos y builds ejecutados, pruebas en dispositivo, problemas conocidos, backlog y siguiente issue.

## Primer issue
“Godot Android: prototipo mínimo de locomoción 3D y HUD”. No comenzar hasta aprobar el stack o registrar una alternativa.
