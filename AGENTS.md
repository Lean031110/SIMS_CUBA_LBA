# AGENTS.md — reglas obligatorias

## Misión
Trabajar en SIMS CUBA LBA: un simulador social de vida cubana para Android con paridad funcional documentada respecto a la experiencia pública de CubitaLife y una implementación original.

## Antes de cada tarea
1. Leer este archivo y README.
2. Leer el estado del proyecto, preguntas abiertas y backlog.
3. Revisar el estado del repositorio y los últimos commits.
4. Verificar la vigencia de fuentes, precios, límites, SDKs y políticas.
5. Definir criterios de aceptación y riesgos antes de modificar archivos.

## Investigación y propiedad intelectual
- Investigar solo información pública y pantallas a las que el usuario tenga acceso legítimo.
- No eludir login, paywalls, controles de acceso, rate limits ni medidas anti-bot.
- No extraer ni reutilizar código privado, assets, modelos, texturas, audio, textos expresivos, logotipos o diseños identificables de CubitaLife.
- Se permite documentar funciones y comportamientos observables para implementar una alternativa independiente.
- No crear cuentas, comprar moneda, publicar, contactar jugadores ni modificar datos de terceros.
- Marcar todo hallazgo como CONFIRMED, DOCUMENTED, HYPOTHESIS, PROPOSAL o PENDING.

## Desarrollo
- Android nativo es la primera plataforma. No sustituirlo por una WebView simple sin ADR aprobado.
- Tecnología provisional: Godot 4.x + GDScript.
- Separar presentación, mundo, dominio, red, almacenamiento y contenido.
- El servidor será autoridad para moneda, inventario, trabajos, progreso, relaciones y acciones con consecuencias.
- El cliente nunca decide por sí solo saldo, recompensas ni inventario final.
- Usar operaciones idempotentes y ledger auditable.
- No guardar secretos, tokens, credenciales, claves de firma ni datos personales en Git.
- No añadir pagos reales hasta aprobar políticas, proveedor, reembolsos y privacidad.

## Calidad y cambios
- Cada cambio de código incluye pruebas y manejo de errores.
- No declarar una build exitosa si no se ejecutó.
- Trabajar en ramas docs/, feat/, fix/ o research/.
- Mantener PRs pequeños; no hacer force-push a main.
- No cambiar licencia, pagos, edad, visibilidad o marca sin autorización explícita.
- Entregar archivos cambiados, evidencia, pruebas, riesgos y siguiente tarea.
