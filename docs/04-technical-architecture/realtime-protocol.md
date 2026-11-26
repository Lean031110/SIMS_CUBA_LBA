# Protocolo realtime v0 — propuesta

No usar hasta que el spike de red apruebe latencia, orden y consumo.

## Transporte
HTTPS para comandos/consultas y WSS para presencia/estado de zona. Mensajes JSON versionados al inicio; medir MessagePack/Protobuf si el volumen lo exige.

## Sobre de mensaje
{version, type, request_id, timestamp, payload}.

## Tipos propuestos
hello, join_zone, leave_zone, input, snapshot, presence, chat, ack, error y resync.

## Reglas
- Validar esquema y tamaño de cada payload.
- Secuenciar comandos sensibles y deduplicar por request_id/idempotency key.
- Snapshot inicial, deltas, heartbeat y resincronización al reconectar.
- Limitar velocidad de acciones y texto; no confiar en timestamp del cliente.
- Segregar mensajes privados de broadcast de zona.
- No aceptar eventos de cliente que alteren saldo o recompensas.

## Pendiente
Definir tick, frecuencia de snapshots, interés espacial, interpolación, lag compensation y capacidad por zona mediante prototipo y carga.