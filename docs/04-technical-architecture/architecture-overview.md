# Visión general de arquitectura

El producto se separa en cliente Android Godot, API de dominio y servidor realtime por zonas. El cliente renderiza el mundo y propone acciones. El servidor valida y persiste todas las consecuencias económicas y de progreso. El almacenamiento guarda perfiles, estados y un ledger auditable. Las interfaces de transporte y repositorios deben permitir migrar de proveedor.

~~~mermaid
flowchart LR
 A[Android Godot] -->|HTTPS| B[Gateway API]
 A -->|WSS| C[Zone Runtime]
 B --> D[(Persistencia global por decidir)]
 C --> E[(Estado de zona)]
 B --> F[Identity / Validation]
 C --> G[Presence / Zone State]
~~~

## Interpretación
- Gateway API: candidato Cloudflare Worker.
- Zone Runtime: candidato Durable Object; comparar Colyseus/Nakama self-hosted.
- Persistencia global: D1, DO SQLite o PostgreSQL; no elegida.
- Estado de zona: puede vivir en DO SQLite, pero la política de snapshots/restore debe probarse.
- Wallet, inventario y progreso requieren transacciones e idempotencia en servidor.

El diagrama describe la propuesta de nuestro sistema; no la arquitectura interna de CubitaLife. No hay backend desplegado.
