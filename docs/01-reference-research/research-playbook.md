# Playbook de investigación continua

## Objetivo
Cerrar evidencia funcional de CubitaLife con observación legítima y convertirla en requisitos independientes de SIMS CUBA LBA.

**Última revisión:** 28-11-2026.

## Prioridad actual
El recorrido del 26-11 abrió muchos módulos, pero empezó con la partida ya cargada. No hubo nueva sesión en la revisión del 28-11. El vacío que más desbloquea es **onboarding → personaje → spawn → movimiento/cámara → edificio/transición**. Sin eso no se puede especificar el bucle básico de juego ni el control táctil Android.

## Orden de recorrido
1. Portada, registro/login, validaciones y recuperación (sin mostrar credenciales).
2. Creación/selección de personaje y personalización (sin crear cuentas duplicadas ni borrar progreso).
3. Primer spawn, tutorial, estado inicial y variaciones.
4. Movimiento, cámara, colisión, selección de edificios y entrada/salida.
5. HUD, cartera, necesidades, misiones y cambios temporales.
6. Trabajo/estudio; vivienda/muebles; comida/salud.
7. Negocios, mercado, inventario, banco y viajes; solo vistas y previsualizaciones antes de confirmar operaciones.
8. Ajustes, privacidad, perfil, chat, DM y CubaGram; no enviar ni publicar.
9. Android: orientación, pausa/reanudación, pérdida de red y recuperación, solo si se puede hacer sin riesgo de perder datos.

## Registro por interacción
ID, fecha, fuente, dispositivo/plataforma, estado inicial, precondición, acción exacta, resultado inmediato, cambios observables, error, persistencia tras recargar (si se prueba), captura/timestamp, estado principal y confianza.

## Estados principales
- CONFIRMED: observado directamente. Indicar si es UI o acción/resultado.
- DOCUMENTED: declarado por fuente primaria oficial.
- HYPOTHESIS: inferencia no probada.
- PROPOSAL: diseño propio para SIMS CUBA LBA.
- PENDING: falta evidencia o decisión.

## Seguridad
No registrar contraseñas, correo completo, tokens, identificadores, saldos privados, chats ni nombres de terceros. No comprar, vender, transferir, apostar, adoptar, publicar, contactar jugadores, aceptar empleos ni cambiar titularidad durante el walkthrough. Detenerse antes de cualquier confirmación irreversible o que consuma moneda.

## Capturas
Seguir [plan de captura 27-11](../../evidence/observations/next-session-capture-plan-2026-11-27.md). La grabación original no se sube a Git. Redactar datos privados antes de compartir.

## Finalización
Una acción pasa a CONFIRMED como comportamiento solo si hay secuencia reproducible con precondición y resultado visible. Persistencia requiere prueba separada. Una etiqueta o botón solo confirma que existe UI.
