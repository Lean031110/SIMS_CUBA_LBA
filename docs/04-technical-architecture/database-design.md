# Diseño de base de datos

Usar relaciones y constraints para identidad, personajes, localización, saldo, inventario, progreso, relaciones y moderación. Las tablas monetarias deben usar ledger inmutable y transacciones. Separar eventos de auditoría de tablas de estado materializado.

## Buenas prácticas
- UUID/IDs no enumerables para entidades públicas.
- UTC en timestamps; formato de moneda/cantidad explícito.
- Constraints y claves de idempotencia.
- Índices basados en consultas medidas.
- Migraciones versionadas, backups y pruebas de restauración.
- Minimizar datos personales y definir retención.
- No exponer email ni identificadores internos a clientes.

El esquema exacto dependerá del motor y del diseño de dominio aprobado.