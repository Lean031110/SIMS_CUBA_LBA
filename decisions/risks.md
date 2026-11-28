# Registro de riesgos — revisión 27-11-2026

| Riesgo | Impacto | Mitigación / gate |
|---|---|---|
| Falta de evidencia de onboarding, spawn y locomoción | Muy alto: diseñar el bucle principal a ciegas | Captura autorizada; no cerrar GDD ni controles hasta observar acción y resultado |
| Copiar assets/marca/código | Legal y reputacional | Recursos originales y revisión de licencias |
| Alcance excesivo | Alto | Paridad incremental y vertical slice |
| Bajo rendimiento Android | Alto | Perfilado temprano en hardware real |
| Incompatibilidad entre Godot estable y target API 36 | Alto: APK no apto para Google Play o toolchain inestable | Comparar 4.7.2 estable y 4.8 RC 1; no fijar toolchain hasta inspeccionar APK |
| Adoptar Godot 4.8 RC antes de estable | Alto: regresiones o cambios en export templates | Mantener RC como experimento; repetir gate con release estable |
| SDK Colyseus Godot en beta | Medio/alto: fallos de exportación o cambios incompatibles | Validar GDExtension en Android arm64 y fijar versión; mantener adapter alternativo |
| SDK Nakama no validado en Android objetivo | Medio/alto: integración/ABI/consumo desconocidos | Prototipo mínimo y benchmark de cliente antes de decisión |
| Superar cuotas de hosting gratuito | Alto: requests fallidos, desconexiones o gasto | Alertas, límites, pruebas de carga, fallback y portabilidad; no usar Free como SLA |
| Hibernation confundida con WebSocket gratis/ilimitado | Alto: factura o interrupción inesperada | Medir mensajes/minuto, tiempo activo y coste; establecer budget limit |
| Latencia desde redes de Cuba | Alto: mala experiencia aunque el datacenter esté disponible | Medir p50/p95 desde redes reales, con pérdida y jitter; diseñar reconexión |
| Estado local como autoridad | Muy alto | Server authority, ledger e idempotencia |
| Red inestable | Alto | Reconnect, snapshots y recuperación |
| Chat sin moderación | Alto | No abrir sin bloqueo/reporte/moderación |
| Pérdida de datos | Muy alto | Backups probados y exportación |
| Monetización/edad no revisadas | Alto | No activar pagos antes de revisión |
| Dependencia de proveedor gratuito con suspensión/expiración | Alto | Copias exportables, restauración y plan de migración a servidor pagado |
