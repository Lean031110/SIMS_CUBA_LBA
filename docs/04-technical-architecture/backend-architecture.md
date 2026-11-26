# Arquitectura del backend

## Componentes del piloto
- API Gateway en Cloudflare Worker: auth, validación, rate limits y versionado.
- Zone Runtime por zona/sala en Durable Object: presencia, secuenciación y estado realtime transitorio.
- D1/SQLite inicial: perfiles, personajes, progresión, inventario y ledger.
- Object storage/CDN: assets propios versionados.

## Autoridad del servidor
Nunca aceptar del cliente saldo, inventario, premio ni éxito de trabajo como verdad. El cliente envía intención; el servidor valida precondiciones, ejecuta operación idempotente, guarda evento y responde con resultado.

## Dominios sugeridos
Identity, Player, Needs, Wallet, Inventory, Activities, World/Zone, Social, Moderation, Notifications y Admin. Mantener módulos separados aunque compartan despliegue.

## Observabilidad
Medir latencia, errores, conexiones, desconexiones, consumo de cuotas y anomalías económicas. No registrar contraseñas, tokens ni mensajes privados.

## Migración
Abstraer repositorios y eventos para migrar D1 a PostgreSQL y Durable Objects a servidor dedicado si escala o coste lo requieren.