# Esquema de datos v1 — borrador

Esquema conceptual; no desplegar migraciones sin ADR y validación.

- users: id, email normalizado, password_hash/identity_provider, created_at, status.
- characters: id, user_id, display_name, appearance_json, home_id, created_at, updated_at.
- player_state: character_id, needs_json, location_id, position, last_seen, version.
- wallets: character_id, currency_code, cached_balance, version.
- wallet_ledger: id, character_id, currency_code, delta, reason_code, reference_id, idempotency_key, created_at.
- inventory_items: id, character_id, item_code, quantity, metadata_json, version.
- activity_sessions: id, character_id, activity_code, started_at, finished_at, result_code.
- zones: id, zone_code, capacity_target, config_version.
- moderation_reports: id, reporter_id, target_id, category, status, created_at.

## Integridad
Ledger append-only; cambios de saldo mediante transacción; claves únicas para idempotencia; foreign keys; timestamps UTC; versiones optimistas; retención y cifrado de PII definidos antes de producción.

## Datos aún desconocidos
La referencia no ha confirmado monedas, inventario, niveles, trabajos ni relaciones internas. Son propuestas para nuestro juego, no afirmaciones sobre CubitaLife.