# Arquitectura del cliente Android

## Capas
1. Presentation: HUD, menús, navegación y accesibilidad.
2. World: escena, avatar, cámara, animaciones, colisión, streaming y LOD.
3. Domain: necesidades, actividades, inventario y viajes según reglas aprobadas.
4. Networking: autenticación, API versionada, WebSocket y reconexión.
5. Persistence: caché local no autoritativa y ajustes.

## Reglas
- Godot 4.x + GDScript provisional; validar en dispositivo antes de congelar.
- UI táctil: joystick izquierdo, cámara por gesto, acción contextual; controles configurables.
- No enviar inputs a 60Hz si no hace falta; interpolar y limitar frecuencia.
- La lógica local es predictiva/visual; saldo, inventario, recompensas y progreso se confirman en servidor.
- Aplicar presets de calidad, LOD, compresión de texturas y carga asíncrona.
- Gestionar pausa/reanudación Android, reconexión con backoff y resincronización.

## Escenas iniciales propuestas
Boot, Login, MainWorld, PlayerAvatar, HUD y LoadingTransition. Son propuestas de estructura, no pantallas confirmadas de CubitaLife.

## Pruebas mínimas
Un dispositivo Android bajo y uno medio: FPS, RAM, tamaño, tiempo de arranque/carga, temperatura, batería, pérdida de red, resume y controles multitáctiles.