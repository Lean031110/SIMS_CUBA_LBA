# Comparativa de hosting — revalidada 27-11-2026

Los límites, precios y planes cambian. “Gratis” significa cuotas y condiciones; no equivale a SLA, disponibilidad continua ni producción ilimitada.

| Plataforma | Free/entrada consultada | Capacidades relevantes | Veredicto para SIMS CUBA LBA |
|---|---|---|---|
| Cloudflare Workers + Durable Objects SQLite | Workers Free: 100k requests/día y 10 ms CPU. DO Free: 100k requests/día, 13k GB-s/día, 5M filas leídas/día, 100k escritas/día, 5 GB SQLite y 100 clases | WebSockets por zona y Hibernation; límites Free separados y operaciones fallan al excederlos | Candidato fuerte para spike serverless por zona; medir carga y facturación antes de decidir |
| Vercel Hobby | WebSockets GA desde 20-10-2026; Function máximo 300 s con Fluid Compute | Funciones y WebSockets comparten límites/precios; reconexión y estado externo | Excelente para web pública/API/lobby; no asumir conexión persistente indefinida |
| Supabase Free | Realtime: 200 conexiones concurrentes y 100 mensajes/s; baja actividad puede pausar proyecto tras 7 días | Auth, PostgreSQL, Storage y Realtime integrados | Útil para cuentas/datos auxiliares o chat pequeño; no sustituye servidor autoritativo del mundo |
| Firebase Realtime Database Spark | 100 conexiones simultáneas, 1 GB almacenado y 10 GB/mes descargados | Realtime simple; Blaze permite hasta 200k conexiones por base y factura excedentes | Alternativa de prototipo pequeño de presencia/chat; reglas, descargas y costes deben controlarse |
| Render Free | 750 horas/mes por workspace; spin-down tras 15 min; arranque ~1 min; Postgres Free expira a 30 días | Servicios web y DB de demostración | Solo pruebas; filesystem efímero y suspensión lo descartan como mundo persistente |
| Fly.io | Máquina always-on mínima desde aprox. 2,19 USD/30 días (256 MB) en regiones de menor coste; disco y egress aparte | Máquinas por segundo, regiones y almacenamiento persistente | Opción de bajo coste pagada para un servidor dedicado de prueba; no es Free |
| Colyseus self-hosted | Framework open source; el coste es la máquina/operación | Rooms, matchmaking, sincronización autoritativa y SDK Godot | Candidato a servidor de juego dedicado si el spike de DO no cubre el modelo |
| Nakama self-hosted | Backend open source; el coste es la máquina/operación | Autenticación, lógica autoritativa, chat y funciones sociales | Candidato más completo para backend de juego/social; revisar consumo y complejidad |

## Hallazgos que cambian la evaluación

### Cloudflare
- DO Free solo permite SQLite para nuevas clases.
- La cuota de DO no debe confundirse con la cuota de Workers: ambos límites aplican.
- Hibernation reduce la duración facturable mientras no hay eventos, pero no elimina el coste de procesar mensajes ni los límites de requests.
- La documentación oficial ilustra un escenario de 10.000 conexiones, 100 DO y un mensaje/minuto con Hibernation por 20,65 USD/mes en Paid, según sus supuestos. No extrapolar ese valor al juego sin un perfil de tráfico real.

### Vercel
- WebSockets está en disponibilidad general desde 20-10-2026.
- Con Fluid Compute, Hobby tiene máximo de 300 segundos; Pro/Enterprise 800 segundos y un máximo extendido de 1.800 segundos en beta.
- La duración máxima de Function limita la vida de la conexión; el cliente debe reconectar, reautenticarse y recuperar snapshot desde almacenamiento externo.

### Supabase y Firebase
- Supabase Free ofrece más conexiones Realtime que Firebase Spark en el límite documentado (200 frente a 100), pero puede pausar proyectos con poca actividad de base de datos durante siete días.
- Firebase Spark no requiere método de pago y tiene 100 conexiones simultáneas para Realtime Database; Blaze eleva el límite de conexiones pero es pay-as-you-go.
- Ambos pueden ser útiles para prototipos auxiliares. Ninguno debe convertirse sin diseño adicional en la autoridad del movimiento, wallet, inventario, trabajo o economía.

### Render y Fly.io
- Render Free no mantiene un servidor de juego siempre encendido y su Postgres Free expira a los 30 días.
- Fly.io es una alternativa de pago por uso, no una opción gratis; el precio final depende de región, RAM, almacenamiento, IP y transferencia.

## Recomendación por etapa
- Web pública, landing y documentación: Vercel o Cloudflare Pages.
- Spike de multijugador: comparar Cloudflare DO Hibernation con Colyseus/Nakama self-hosted.
- Auth/SQL/chat auxiliar: medir Supabase o Firebase solo si simplifican el prototipo sin introducir dependencia innecesaria.
- Demo siempre disponible: servidor dedicado pequeño con coste explícito y backups; no Render Free.
- Producción: decidir después de medir carga real, latencia desde redes cubanas, concurrencia, coste por usuario y recuperación.

No se aprueba proveedor de producción en esta revisión.
