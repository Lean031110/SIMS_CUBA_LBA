# SIMS CUBA LBA — Android Life Simulator

> Documentación, investigación de referencia y plan técnico para crear un simulador social de vida ambientado en Cuba, con Android como plataforma principal.

**Estado:** investigación y preproducción. El repositorio estaba vacío al inicio de esta intervención; este primer commit incorpora documentación y controles de proyecto, no una implementación jugable.

**Referencia funcional investigada:** https://cubitalife.com/  
**Repositorio:** https://github.com/Lean031110/SIMS_CUBA_LBA  
**Nombre de trabajo:** SIMS CUBA LBA. El nombre final, identidad visual y marca quedan pendientes de decisión.

## Objetivo del proyecto

Construir para Android una experiencia de simulación social de vida cubana que alcance paridad funcional con las características públicas que puedan verificarse de CubitaLife. La implementación será independiente: código, personajes, modelos, texturas, escenarios, música, textos, interfaz y marca originales. La paridad se medirá por capacidades y flujos del jugador, no por copiar código, archivos privados ni recursos protegidos.

**Orden de producto:**
1. Investigar y documentar la experiencia de referencia con evidencia.
2. Cerrar el alcance de paridad funcional y los requisitos Android.
3. Crear un prototipo técnico y una primera zona vertical.
4. Completar la línea base de funciones verificadas.
5. Solo entonces priorizar mejoras propias y diferenciadoras.

## Estado actual

- Repositorio público de GitHub, rama principal `main`; inicialmente estaba vacío.
- Investigación pública inicial de la portada y términos completada el 26-11-2026.
- La experiencia autenticada, los sistemas internos y la interacción real con controles siguen pendientes.
- Motor recomendado provisionalmente: Godot 4.x con GDScript, orientado a Android nativo.
- Backend de prototipo recomendado para prueba: Cloudflare Workers + Durable Objects + D1/SQLite; sujeto a un benchmark real y límites gratuitos.
- Vercel puede servir la web pública y APIs/WebSockets acotados, pero no se recomienda como único host de un mundo multijugador persistente.
- No hay cliente, servidor ni APK implementados todavía.

## Estructura

- `AGENTS.md` — instrucciones generales para agentes de IA.
- `.github/copilot-instructions.md` — reglas de Copilot en este repositorio.
- `docs/00-project/` — estado, alcance e índice.
- `docs/01-reference-research/` — CubitaLife, inventario de funciones, evidencias y lagunas.
- `docs/02-product-vision/` — visión y principios de producto.
- `docs/03-game-design/` — especificación de paridad Android y bucles de juego.
- `docs/04-technical-architecture/` — motor, cliente, backend, red, datos y ADRs.
- `docs/05-platforms/` — requisitos Android y compilación.
- `docs/06-production/` — roadmap, backlog y QA.
- `docs/07-deployment/` — hosting y estrategia de despliegue.
- `docs/08-agent-workflow/` — roles, protocolos y tarea diaria de investigación.
- `evidence/` — registro de fuentes, observaciones y futuras capturas propias.
- `diagrams/` — diagramas Mermaid.
- `decisions/` — supuestos, preguntas y riesgos.

## Empezar con agentes

1. Leer `AGENTS.md` completo.
2. Leer `docs/00-project/current-status.md`.
3. Leer `docs/01-reference-research/cubitalife-deep-research.md` y `known-features-inventory.md`.
4. Continuar con `docs/08-agent-workflow/ANDROID_IMPLEMENTATION_AGENT.md`.
5. No empezar por generar todo el juego en un solo paso. Primero ejecutar el hito de prototipo y sus criterios de aceptación.

## Regla de evidencia

Todo hallazgo debe etiquetarse como `CONFIRMED`, `DOCUMENTED`, `HYPOTHESIS`, `PROPOSAL` o `PENDING`. Ningún agente puede presentar una hipótesis como característica real de CubitaLife. Añadir URL, fecha de consulta, tipo de evidencia y nivel de confianza en `evidence/source-register.md`.

## Licencia y propiedad intelectual

La licencia del código aún no está decidida. Ver `LICENSE_DECISION.md`. No introducir recursos de CubitaLife ni de terceros sin una licencia compatible y documentada.
