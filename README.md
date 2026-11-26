# SIMS CUBA LBA — Android Life Simulator

> Documentación, investigación de referencia y plan técnico para crear un simulador social de vida ambientado en Cuba, con Android como plataforma principal.

**Estado:** investigación y preproducción. Este repositorio contiene documentación y controles del proyecto, no una implementación jugable ni un APK.

**Referencia funcional investigada:** https://cubitalife.com/  
**Repositorio:** https://github.com/Lean031110/SIMS_CUBA_LBA  
**Nombre de trabajo:** SIMS CUBA LBA. El nombre final, identidad visual y marca quedan pendientes de decisión.

## Objetivo
Construir para Android una experiencia social de simulación de vida cubana que alcance paridad funcional con las capacidades de CubitaLife que puedan verificarse. La implementación será independiente: código, personajes, modelos, texturas, escenarios, música, textos, interfaz y marca originales. La paridad se medirá por capacidades y flujos del jugador, no por copiar código, assets ni pantallas protegidas.

## Hallazgo principal — sesión real
El 26-11-2026 se revisó una grabación de una sesión autenticada en Chrome para Android. La partida mostraba Camagüey, un mundo isométrico con establecimientos/avatares y un HUD con cartera, diamantes y cuatro necesidades. El teléfono virtual abría módulos de trabajo, universidad, negocios, vivienda, muebles, mercado, inventario, salud, comida, viajes, banco, inversión, pareja/familia, música, ciudad, relojes, anuncios y CubaGram.

**Importante:** se inspeccionaron pantallas, no se completaron transacciones. El vídeo original no se sube porque contiene identificadores de cuenta y nombres de otros jugadores. El detalle cronológico y los límites de evidencia están en [la observación de sesión](evidence/observations/session-android-2026-11-26.md).

## Orden de producto
1. Investigar/documentar comportamientos con evidencia.
2. Cerrar el alcance de paridad funcional y requisitos Android.
3. Crear prototipo técnico y una primera zona vertical.
4. Completar línea base priorizada de capacidades verificadas.
5. Priorizar mejoras propias y diferenciadoras después.

## Estado actual
- Rama principal main; trabajo de investigación en ramas research/.
- Sesión móvil real visualmente auditada; comportamiento transaccional y persistencia siguen pendientes.
- Motor provisional: Godot 4.x + GDScript, sujeto a benchmark Android.
- Backend de prototipo: Cloudflare Workers + Durable Objects + D1/SQLite, sujeto a benchmark y límites gratuitos.
- Vercel puede servir web pública y APIs/WebSockets acotados, pero no se recomienda como único host de mundo persistente.
- No hay cliente, servidor ni APK implementados.

## Estructura
- AGENTS.md — instrucciones obligatorias para agentes.
- .github/copilot-instructions.md — reglas de Copilot.
- docs/00-project/ — estado, alcance e índice.
- docs/01-reference-research/ — investigación de CubitaLife, inventario y análisis.
- docs/02-product-vision/ — visión y principios.
- docs/03-game-design/ — especificación de paridad y GDD.
- docs/04-technical-architecture/ — motor, cliente, backend, red, datos y ADRs.
- docs/05-platforms/ — requisitos Android y compilación.
- docs/06-production/ — roadmap, backlog y QA.
- docs/07-deployment/ — hosting.
- docs/08-agent-workflow/ — roles y tareas de agentes.
- evidence/ — registro de fuentes y observaciones.
- diagrams/ — diagramas Mermaid.
- decisions/ — supuestos, preguntas y riesgos.

## Empezar con agentes
1. Leer AGENTS.md y este README.
2. Leer docs/00-project/current-status.md.
3. Leer docs/01-reference-research/cubitalife-deep-research.md, known-features-inventory.md y cubitalife-gameplay-systems-catalog.md.
4. Leer evidence/observations/session-android-2026-11-26.md.
5. Continuar con docs/08-agent-workflow/ANDROID_IMPLEMENTATION_AGENT.md.
6. No intentar construir todo en un solo paso; comenzar por prototipo y criterios de aceptación.

## Regla de evidencia
Etiquetar cada hallazgo como CONFIRMED_UI, OBSERVED_COPY, DOCUMENTED, HYPOTHESIS, PROPOSAL, NOT_TESTED o PENDING. Un botón observado no demuestra su efecto. Incluir URL, fecha, tipo de evidencia y confianza en evidence/source-register.md.

## Propiedad intelectual y seguridad
No copiar código, recursos, modelos, texturas, audio, marca, textos expresivos ni composiciones visuales exactas de CubitaLife. No almacenar credenciales, tokens ni datos personales. La licencia del código aún no está decidida; ver LICENSE_DECISION.md.
