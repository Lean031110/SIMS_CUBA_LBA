# ADR-002 — Backend y multijugador para prototipo

- Estado: **Cloudflare es candidato para spike; no aprobado para producción**.
- Revisión: 27-11-2026.
- Objetivo: comparar un backend server-authoritative de zonas con alternativas self-hosted antes de fijar arquitectura.

## Candidato A — Cloudflare Workers + Durable Objects

**DOCUMENTED, consulta 27-11-2026:**
- Workers Free: 100.000 requests/día, 10 ms CPU por invocación, 128 MB, 50 subrequests por request y 6 conexiones salientes simultáneas.
- Durable Objects SQLite Free: 100.000 requests/día, 13.000 GB-s/día, 5 millones de filas leídas/día, 100.000 filas escritas/día y 5 GB de almacenamiento total.
- Workers Free solo permite nuevos Durable Objects con backend SQLite; hay un máximo de 100 clases DO en Free.
- Si se excede una cuota Free, las operaciones de ese tipo fallan hasta el siguiente reinicio diario. No es una cuota de producción garantizada.
- WebSocket Hibernation mantiene clientes conectados mientras el objeto está fuera de memoria y reduce duración facturable durante inactividad.
- Los mensajes WebSocket entrantes se facturan con relación 20:1 para el cómputo de requests; la hibernación no hace que el tráfico sea ilimitado ni gratuito.

Fuente de precios DO: https://developers.cloudflare.com/durable-objects/platform/pricing/
Fuente de límites DO: https://developers.cloudflare.com/durable-objects/platform/limits/
Fuente Workers: https://developers.cloudflare.com/workers/platform/limits/
Fuente WebSockets: https://developers.cloudflare.com/durable-objects/best-practices/websockets/

### Diseño candidato
- Worker de entrada: autenticación, validación de token, routing y API.
- Un Durable Object por zona/sala para coordinar presencia y estado de simulación.
- Hibernation WebSocket para conexiones inactivas; snapshots y recuperación tras reinicialización.
- Estado de zona persistente en DO SQLite si el modelo lo justifica.
- Perfil, wallet, inventario y ledger deben persistir con transacciones auditables. La elección D1 vs DO SQLite vs PostgreSQL queda pendiente de prueba de atomicidad, backup, exportación y concurrencia.
- Nunca confiar en saldo, inventario o recompensa calculados solo por el cliente.

**Advertencia de coste:** la página oficial muestra un ejemplo ilustrativo de 10.000 conexiones WebSocket distribuidas en 100 DO, con un mensaje por minuto y Hibernation, que estima 20,65 USD/mes en el plan Paid bajo sus supuestos. No es una previsión para SIMS CUBA LBA; demuestra que la carga de mensajes y el tiempo activo deben medirse.

## Alternativas gestionadas o serverless

| Plataforma | Límite Free/plan relevante | Uso posible | Límite para este proyecto |
|---|---|---|---|
| Vercel Functions/WebSockets | WebSockets GA desde 20-10-2026; Hobby máximo 300 s por Function con Fluid Compute; Pro/Enterprise 800 s, 1800 s en beta | Web pública, API, lobby, chat o sesión acotada | No asumir conexión persistente indefinida; reconexión y estado externo obligatorios |
| Supabase Realtime | Free: 200 conexiones concurrentes y 100 mensajes/s; proyectos Free con poca actividad pueden pausarse tras 7 días | Auth, perfiles, SQL, presencia/chat auxiliar | No sustituye por sí solo lógica autoritativa de simulación; cuotas y pausa |
| Firebase Realtime Database | Spark: 100 conexiones simultáneas, 1 GB y 10 GB/mes; Blaze: hasta 200.000 conexiones por base de datos y facturación de uso | Prototipo pequeño de presencia/chat o sincronización simple | Reglas de seguridad y lógica autoritativa de juego deben diseñarse aparte; controlar descargas y costes |
| Render Free | Spin-down tras 15 min sin tráfico, arranque aproximado 1 min, filesystem efímero y Postgres Free expira a 30 días | Demo y pruebas de servicio | No sirve como mundo persistente siempre encendido |
| Fly.io | Compute por segundo; máquina mínima always-on desde aprox. 2,19 USD/30 días en regiones más baratas; disco/egress aparte | Servidor dedicado pequeño de prueba | No es hosting gratuito; 256 MB no bastan para asumir capacidad de juego sin medir |

Fuentes oficiales: Vercel, Supabase, Firebase, Render y Fly.io listadas en evidence/source-register.md.

## Alternativas self-hosted de juego

- **Colyseus:** framework Node.js open source con rooms, matchmaking, sincronización de estado y SDK Godot. Adecuado para probar rooms autoritativas en un proceso dedicado. Requiere VPS/servidor, base de datos, monitorización y operación propia. https://docs.colyseus.io/
- **Nakama:** backend open source para juegos con autenticación, lógica autoritativa, chat y sistemas sociales. Más completo, pero añade operación y configuración; revisar integración concreta con Godot y recursos de servidor. https://heroiclabs.com/nakama/

Self-hosted significa que el software puede ser gratuito; la máquina, almacenamiento, tráfico, copias y mantenimiento no lo son necesariamente.

## Recomendación provisional
No elegir aún una plataforma final. Ejecutar un spike comparativo:
1. Cloudflare Worker + DO Hibernation para una zona.
2. Colyseus o Nakama en servidor local/VPS de prueba.
3. Firebase/Supabase solo como comparación de presencia/chat y persistencia, no como autoridad automática de economía.

Medir 20, 50 y 100 clientes simulados; tamaño de zona; frecuencia de mensajes; CPU/RAM; latencia p50/p95; reconexión; persistencia; recuperación; tráfico y coste estimado. Repetir desde redes/regiones que representen a jugadores en Cuba.

## Gate de producción
No pasar a producción sin benchmark, alertas de gasto, límite de presupuesto, backups y restore probado, seguridad de cuentas, pruebas de abuso, portabilidad de datos y coste por 100/500/1.000 concurrentes. Ningún tier Free se considera producción 24/7 o ilimitada.
