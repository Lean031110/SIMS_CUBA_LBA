# Networking multijugador

## Principios
- Servidor autoritativo para economía, inventario, progreso y acciones con consecuencias.
- Conexiones por zona para limitar broadcast.
- Interpolación de otros avatares; no replicar cada frame.
- Reconnect con backoff/jitter, snapshots, deduplicación e idempotencia.
- Rate limits por usuario, IP y sala.
- Protección frente a spam, teleporting, replay y abuso de mensajes.

## Primera prueba
Sala con entrada/salida, presencia y movimiento de dos clientes. Medir latencia, ancho de banda, reconexión, orden y carga.

## Escala
No prometer jugadores simultáneos sin medir. Diseñar zonas instanciables y métricas de ocupación, pero fijar capacidad tras pruebas.