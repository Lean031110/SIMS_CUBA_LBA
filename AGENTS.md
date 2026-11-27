# AGENTS.md — reglas obligatorias

## Misión
Preparar SIMS CUBA LBA: simulador social de vida cubana Android-first, con investigación funcional verificable de CubitaLife y una implementación original.

## Antes de cada tarea
1. Leer README, AGENTS, estado, preguntas y backlog.
2. Revisar commit, ramas, PRs y árbol antes de editar.
3. Reutilizar evidencia existente; no repetir investigación ya cerrada sin motivo.
4. Comprobar fuentes, fechas, SDKs, políticas y límites vigentes.
5. Definir criterio de aceptación, riesgo y alcance del cambio.

## Estados de evidencia obligatorios
Usar un único estado principal por hallazgo:
- CONFIRMED: observado directamente en evidencia primaria. Especificar si confirma solo la existencia de UI o también una acción/resultado.
- DOCUMENTED: declarado en una fuente primaria oficial, sin verificación independiente.
- HYPOTHESIS: inferencia no probada.
- PROPOSAL: diseño o decisión sugerida para SIMS CUBA LBA.
- PENDING: sin evidencia suficiente o decisión abierta.

Añadir tipo de evidencia (pantalla, texto, acción, persistencia, fuente oficial), URL/procedencia, fecha de consulta/publicación y confianza. No usar estados secundarios como sustituto de estos cinco.

## Investigación y propiedad intelectual
- Solo información pública y pantallas a las que el propietario tenga acceso legítimo.
- No eludir login, paywalls, controles de acceso, rate limits ni anti-bot.
- No reutilizar código, assets, modelos, texturas, audio, textos expresivos, logos o diseño identificable de CubitaLife.
- No crear cuentas, comprar moneda, publicar, enviar mensajes ni modificar datos de terceros.
- Una captura de una pantalla no demuestra que la operación funcione; registrar precondición, acción, salida y persistencia.

## Desarrollo
- Android instalable nativo es el objetivo primario; no sustituirlo por WebView sin ADR aprobado.
- Godot 4.7.2 + GDScript es candidato, no decisión final hasta benchmark y prueba de target API 36.
- Separar presentación, mundo, dominio, red, almacenamiento y contenido.
- El servidor valida moneda, inventario, trabajos, progreso, relaciones y acciones con consecuencias.
- Usar operaciones idempotentes, ledger auditable, reconexión y recuperación de snapshots.
- No guardar secretos, tokens, credenciales, claves de firma ni datos personales en Git.
- No implementar pagos reales ni definir edad, licencia o marca sin aprobación explícita.

## Calidad y cambios
- Cada cambio de código incluye pruebas y manejo de errores.
- No declarar builds, pruebas físicas ni despliegues si no se ejecutaron.
- Trabajar en ramas docs/, feat/, fix/ o research/.
- No hacer force-push ni merge automático.
- Entregar archivos, evidencia, limitaciones, riesgos y siguiente tarea.
