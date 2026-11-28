# Plan de spike comparativo de backend realtime

**Estado:** PROPOSAL; no ejecutado.
**Objetivo:** elegir una arquitectura de zona/mundo mediante evidencia reproducible, no por cuotas nominales ni marketing.

## Candidatos
1. **Cloudflare:** Worker de entrada + Durable Object por zona, WebSocket Hibernation y persistencia SQLite/D1 por decidir.
2. **Colyseus:** servidor Node.js self-hosted con rooms y estado sincronizado. El GDExtension de Godot figura en beta; validar Android y compatibilidad de versiones antes de invertir en integración.
3. **Nakama:** servidor self-hosted con cliente Godot 4, sockets realtime y matches server-authoritative. Validar la versión exacta del SDK y el flujo Android.

No comparar solo el precio del software. Incluir máquina, base de datos, almacenamiento, tráfico, backups, monitorización, dominio, operación y mantenimiento.

## No objetivos
- No implementar el mundo completo.
- No abrir chat público, feed social ni mensajes privados.
- No usar cuentas reales ni datos de jugadores.
- No mover dinero real ni implementar compras.
- No considerar al cliente como autoridad de economía, inventario o progreso.

## Slice común de prueba
- Una zona vacía con 1–3 avatares de prueba.
- Identidad de prueba mediante tokens no reutilizables fuera del entorno local.
- Entrada/salida de zona y presencia.
- Movimiento sintético con secuencia monotónica de comandos.
- Snapshot autoritativo del servidor con versión.
- Reconexión y recuperación del último snapshot.
- Registro de eventos técnicos sin contraseñas, tokens ni datos personales.

## Perfiles de carga propuestos
Los siguientes son perfiles iniciales de estrés, no estimaciones de concurrencia real ni requisitos finales:
- 20 clientes concurrentes.
- 50 clientes concurrentes.
- 100 clientes concurrentes.
- Perfil base configurable: 5 comandos de movimiento por segundo por cliente y 2 snapshots por segundo por cliente.
- Perfil de ráfaga: duplicar temporalmente la frecuencia de comandos para detectar colas y saturación.
- Payloads, tamaño de zona y frecuencia final deben ajustarse tras medir el prototipo de locomoción y el diseño de red.

## Métricas obligatorias
- RTT y latencia de servidor: p50, p95 y p99.
- Tiempo de join/leave y reconexión.
- Porcentaje de mensajes perdidos, duplicados, fuera de orden o rechazados.
- Tiempo hasta recuperar un snapshot coherente.
- Bytes enviados/recibidos por cliente y por minuto.
- CPU, RAM, event loop, conexiones y reinicios del servidor.
- Requests, duración activa, lecturas, escrituras y uso de cuotas por proveedor.
- Coste proyectado por 100, 500 y 1.000 conexiones simultáneas, con supuestos explícitos.
- Latencia desde una red que represente a Cuba y una región de control; registrar RTT, jitter y pérdida. Una prueba desde otra región no sustituye esta medición.

## Pruebas de fallo y seguridad
1. Cortar conexión del cliente durante 5 s y 30 s.
2. Reiniciar el servidor/instancia con clientes conectados.
3. Repetir el mismo comando con el mismo ID para comprobar idempotencia.
4. Enviar secuencias atrasadas o inválidas y comprobar rechazo.
5. Saturar una zona y verificar rate limits/backpressure.
6. Simular expiración de token y reconexión autenticada.
7. En Cloudflare, comprobar que el objeto puede hibernar y reanudar sin perder estado requerido.
8. Verificar que el cliente no puede fijar su propia posición final ni otorgarse recompensas.

## Criterios de aceptación
- El servidor es autoridad de la posición aceptada y del estado persistente.
- La reconexión recupera un snapshot coherente con versión monotónica.
- Comandos repetidos no duplican efectos.
- Reinicio y pérdida de red no producen pérdida silenciosa de estado confirmado.
- Las operaciones inválidas se rechazan con respuestas trazables.
- Se conocen cuotas, coste y condiciones de fallo de cada opción.
- Se define el umbral p95 después de medir redes objetivo; no inventarlo antes.
- Se documenta cómo hacer backup y restore, y se ejecuta al menos una restauración de prueba antes de aprobar persistencia.

## Entregables
- Repositorio/branch de spike separado de la app principal.
- Tabla de resultados con hardware, región, versiones, configuración y número de clientes.
- Gráficos p50/p95/p99, uso de recursos, tráfico y coste estimado.
- Registro de fallos, bugs y límites observados.
- ADR-002 actualizado con decisión, trade-offs y plan de salida.

## Bloqueos previos
- No ejecutar hasta tener el gate de exportación Android resuelto y una escena/protocolo mínimo definidos.
- No seleccionar región de producción sin medir latencia desde redes objetivo.
- No pasar a producción con un tier Free sin límites, alertas, backup/restore y plan de migración a servidor pagado.
