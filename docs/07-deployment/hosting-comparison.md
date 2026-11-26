# Comparativa de hosting — 26-11-2026

Los planes cambian. “Gratis” significa cuotas y condiciones, no SLA de producción.

| Plataforma | Puede alojar | Límites relevantes consultados | Veredicto |
|---|---|---|---|
| Vercel Hobby | Web, APIs y WebSockets | WebSockets GA desde 20-10-2026. En Hobby cada conexión termina al llegar a 300 s; hay que reconectar y usar estado externo | Bien para web pública y funciones acotadas; no como único mundo persistente |
| Cloudflare Workers + Durable Objects | API, WebSockets por zona, estado coordinado y SQLite | Workers Free: 100k solicitudes/día, 10ms CPU. DO Free SQLite: 100k requests/día, 13k GB-s/día, 5M lecturas/día, 100k escrituras/día, 5GB storage | Mejor candidato para piloto realtime medido |
| Supabase Free | Auth, Postgres, Storage, Realtime auxiliar | Realtime Free: 200 conexiones y 100 mensajes/s; proyectos free se pausan tras 1 semana de inactividad | Útil para auth/chat básico, no para autoridad de simulación |
| Render Free | Web service y DB de demo | Spin-down tras 15 min; Postgres Free expira a 30 días; filesystem efímero | Solo demo/pruebas |
| VPS/servidor dedicado | Proceso persistente y DB propia | Requiere pago y operación | Mejor opción futura para mundo persistente con usuarios |

## Vercel: respuesta concreta
Sí, se puede desplegar parte del sistema allí e incluso WebSockets. La documentación actual indica que cada conexión se mantiene en la instancia que la aceptó y termina al alcanzar la duración máxima. En Hobby, el máximo documentado es 300 segundos. Una reconexión puede llegar a otra instancia; los estados compartidos deben vivir fuera de la memoria de la Function. Es válido para web, lobby, presencia, chat o sesiones acotadas, pero requiere diseñar reconexión y coordinación distribuida.

## Recomendación
- Web pública/documentación: Vercel o Cloudflare Pages.
- Backend realtime piloto: Cloudflare Workers + Durable Objects.
- Datos de jugador: D1/SQLite al inicio; evaluar PostgreSQL antes de producción.
- Assets: object storage/CDN con versionado.
- Mantener interfaces de dominio y exportación de datos para migrar a VPS.
