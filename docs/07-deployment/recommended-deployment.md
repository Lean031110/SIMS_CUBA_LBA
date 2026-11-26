# Plan recomendado de despliegue

## Etapa 0 — Local y CI
Godot Android local, Worker/DO en desarrollo, D1 local y pipeline de validación.

## Etapa 1 — Demo privada
APK debug para testers invitados; Worker + DO + D1 en entorno separado; una zona de baja población y cero pagos reales.

## Etapa 2 — Alpha cerrada
Entornos separados, migraciones y backups; dashboard de conexiones/errores; pruebas escalonadas 20 → 50 → 100 clientes simulados; revisar cuotas.

## Etapa 3 — Beta pública
No depender de tiers con suspensión/expiración si se requiere continuidad. Evaluar compute dedicado, PostgreSQL, backups y monitorización. Publicar políticas, clasificación, normas y soporte.

## Portabilidad
Dominio separado del proveedor; capa de almacenamiento intercambiable; protocolo versionado; exportar datos y probar restore periódicamente.

## Diagrama
Android Godot Client → HTTPS API → Worker Gateway → Identity/Game APIs → D1.  
Android Godot Client → WSS → Zone Durable Object → estado cercano/presencia y persistencia.
