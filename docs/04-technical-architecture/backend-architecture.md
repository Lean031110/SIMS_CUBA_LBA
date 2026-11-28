# Arquitectura del backend — propuesta no aprobada

## Componentes candidatos del piloto
- API Gateway en Cloudflare Worker: autenticación, validación, rate limits y versionado.
- Zone Runtime por zona/sala en Durable Object: presencia, secuenciación y estado realtime.
- Persistencia global: D1, SQLite de Durable Objects o PostgreSQL. **No está elegida**; debe compararse atomicidad, backup, restore, exportación, concurrencia y coste.
- Object storage/CDN: assets propios versionados.
- Alternativa a DO: Colyseus o Nakama self-hosted para probar un proceso de juego autoritativo.

## Autoridad del servidor
Nunca aceptar del cliente saldo, inventario, premio ni éxito de trabajo como verdad. El cliente envía intención; el servidor valida precondiciones, ejecuta operación idempotente, guarda evento y responde con resultado.

## Dominios sugeridos
Identity, Player, Needs, Wallet, Inventory, Activities, World/Zone, Social, Moderation, Notifications y Admin. Mantener módulos separados aunque compartan despliegue.

## Observabilidad
Medir latencia, errores, conexiones, desconexiones, consumo de cuotas y anomalías económicas. No registrar contraseñas, tokens ni mensajes privados.

## Migración
Abstraer repositorios y eventos para migrar D1/DO SQLite a PostgreSQL y Durable Objects a servidor dedicado si la escala, latencia o coste lo requieren.

## Gate
No elegir persistencia ni proveedor hasta probar operaciones atómicas del ledger, idempotencia, recuperación de sala, reconexión, backups y restore. Consultar ADR-002 y hosting-comparison.md para límites y alternativas.


## Spike comparativo
El proveedor de zona y el SDK cliente siguen sin decidir. Seguir [backend-spike-plan.md](backend-spike-plan.md) para comparar Cloudflare DO, Colyseus y Nakama con el mismo protocolo, clientes sintéticos, métricas de latencia/recuperación/coste y pruebas de fallo. La GDExtension de Colyseus para Godot figura en beta; no asumir estabilidad Android.
