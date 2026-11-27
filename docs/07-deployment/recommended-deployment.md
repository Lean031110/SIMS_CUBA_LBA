# Plan recomendado de despliegue — revisión 27-11-2026

## Etapa 0 — local y CI
- Godot 4.7.2 estable como candidato.
- Spike de exportación Android con target API 36.
- Backend local simulado para validar protocolo y autoridad.
- Pruebas unitarias de dominio, migraciones y serialización.
- No se requiere proveedor cloud para construir la primera escena.

## Etapa 1 — prototipo privado
- APK debug para testers autorizados.
- Una zona original pequeña y pocos clientes.
- Comparar Cloudflare DO Hibernation con Colyseus/Nakama local o en una VM.
- Persistencia y economía con cuentas de prueba y datos ficticios.
- Cero pagos reales, apuestas, transferencias entre usuarios o publicaciones públicas.

## Etapa 2 — alpha cerrada
- Entornos separados de desarrollo, test y producción.
- Migraciones, backups y restore ensayado.
- Panel de conexiones, errores, latencia y gasto.
- Pruebas escalonadas 20 → 50 → 100 clientes simulados.
- Medir latencia desde redes que representen Cuba, no solo desde el datacenter del proveedor.
- Definir umbral de gasto y apagado seguro de recursos.

## Etapa 3 — beta pública
- No depender de tiers con suspensión, expiración de base de datos o cuotas que puedan detener operaciones.
- Evaluar servidor dedicado, PostgreSQL administrado, backups y monitorización.
- Publicar política de privacidad, edad, reglas, clasificación, moderación y soporte después de aprobación.

## Portabilidad
- Dominio separado del proveedor.
- Protocolo versionado.
- Capa de almacenamiento intercambiable.
- Exportación de cuentas y progreso.
- Pruebas periódicas de restauración.
- No acoplar la economía a una API propietaria sin estrategia de migración.

## Diagrama conceptual
Android Godot Client → HTTPS API → Gateway/Identity → servicios de cuenta y juego.  
Android Godot Client → WSS → servidor de zona autoritativo → snapshots/presencia.  
La persistencia global de cuenta, wallet, inventario y ledger debe estar separada del estado efímero de la sala.

## Decisión
El plan es una propuesta de preproducción. No hay infraestructura desplegada ni proveedor aprobado para producción.
