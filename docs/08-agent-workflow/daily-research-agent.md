# Tarea diaria de investigación — instrucciones

## Objetivo
Revisar el estado, identificar el vacío que más desbloquea el proyecto y continuar sin repetir búsquedas ya resueltas.

## Ciclo
1. Leer README, AGENTS, current-status, source register, inventario, catálogo, observaciones, GDD, ADR, preguntas, riesgos y backlog.
2. Revisar main, ramas research, PR abiertos, último commit y diferencias; no asumir que una rama está fusionada.
3. Elegir el gap pendiente que desbloquee más módulos. Mientras no exista una nueva captura, priorizar onboarding/personaje/spawn/movimiento/cámara.
4. Buscar fuentes actuales y oficiales solo para puntos que cambian o no están documentados; registrar URL, fecha de publicación/actualización, fecha de consulta y confianza.
5. Si se requiere interacción, usar solo una sesión legítima o material compartido por el propietario. No acceder con credenciales compartidas por chat ni eludir controles.
6. Añadir fuente, observación y confianza; actualizar inventario, GDD, preguntas, riesgos, ADR, backlog y source register según corresponda.
7. Mantener estados principales CONFIRMED, DOCUMENTED, HYPOTHESIS, PROPOSAL y PENDING. Especificar si CONFIRMED solo aplica a UI o a una acción ejecutada.
8. No registrar contraseñas, correos completos, tokens, saldos privados, chats ni datos de terceros.
9. Revalidar SDKs, versiones, cuotas, precios y límites antes de tomar decisiones técnicas o desplegar.
10. Revisar contradicciones, enlaces rotos, duplicados, estado de PR y vigencia de las fuentes.
11. Si hay escritura, crear/usar una rama research/fecha-tema, revisar diff y abrir PR; no hacer merge automático.
12. Reportar lo nuevo verificado, cambios, pendientes, bloqueos y siguiente experimento.

## Prioridad
A. Onboarding/personaje/spawn/movimiento/cámara. B. HUD/necesidades/cartera. C. Trabajo/estudio. D. Vivienda/muebles. E. Negocios/mercado/inventario. F. Viajes/ciudad. G. Social/CubaGram/chat y moderación. H. Ajustes/privacidad/Android. I. Godot toolchain/API target. J. Backend, carga, coste y latencia.

## Commits y PR
Preferir PRs pequeños y apilados cuando ya exista una investigación abierta. No duplicar PRs con el mismo diff. No hacer force-push ni merge automático en decisiones de producto, economía, seguridad o arquitectura. Si no hay acceso autorizado al repo, entregar un parche y explicar el bloqueo.
