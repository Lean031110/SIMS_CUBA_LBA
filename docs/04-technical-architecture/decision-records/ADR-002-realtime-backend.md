# ADR-002 — Backend y multijugador para prototipo

- Estado: candidato preferido para prueba; no aprobado para producción.
- Fecha: 26-11-2026.
- Propuesta: Cloudflare Workers + Durable Objects con WebSocket Hibernation + D1/SQLite.

## Motivos
- Durable Objects soportan WebSockets y recomiendan Hibernation para ahorrar duración facturable en inactividad: https://developers.cloudflare.com/durable-objects/best-practices/websockets/
- Durable Objects con SQLite están disponibles en Workers Free. Las cuotas publicadas incluyen 100.000 requests/día, 13.000 GB-s/día, 5M rows read/día, 100k rows write/día y 5 GB de SQLite total: https://developers.cloudflare.com/durable-objects/platform/pricing/
- Workers Free publica 100.000 requests/día, 10 ms CPU por invocación y 128 MB RAM: https://developers.cloudflare.com/workers/platform/limits/

## Diseño
- Un Durable Object por zona/sala controla la sesión y estado visible.
- Worker enruta autenticación, API, conexiones y selección de zona.
- D1/SQLite guarda perfiles, saldo, inventario, progreso y ledger.
- Estado de zona transitorio en DO; persistir datos importantes.
- Agrupar mensajes y controlar frecuencia.

## Riesgos
Cuotas diarias, límites de ejecución, costes al escalar y necesidad de pruebas de carga. Superar límites puede hacer fallar operaciones. No garantiza coste cero ni capacidad para grandes poblaciones.

## Alternativas
- Vercel Functions soportan WebSockets, pero una conexión se cierra al llegar a duración máxima; en Hobby son 300 s. Requiere reconectar y usar almacén externo para estado compartido: https://vercel.com/kb/guide/do-vercel-serverless-functions-support-websocket-connections
- Supabase Realtime Free documenta 200 conexiones y 100 mensajes/s: https://supabase.com/docs/guides/realtime/limits
- Render Free se duerme tras 15 min sin tráfico y Postgres gratuito expira tras 30 días: https://render.com/docs/free
- VPS/servidor dedicado será alternativa de producción cuando exista presupuesto.

## Gate
No pasar a producción sin benchmark con bots/clientes Android, coste por 100/500/1.000 concurrentes, alertas y recuperación tras caída/reconexión.
