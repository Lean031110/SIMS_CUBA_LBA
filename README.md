# SIMS CUBA LBA — simulador de vida cubana para Android

> Investigación, diseño y preparación técnica de un simulador social de vida ambientado en Cuba. Android instalable es la plataforma principal.

**Estado al 27-11-2026:** fase 0 — investigación y preproducción. No hay código jugable, servidor, APK ni despliegue del juego.

**Referencia funcional pública:** https://cubitalife.com/  
**Repositorio:** https://github.com/Lean031110/SIMS_CUBA_LBA  
**Nombre de trabajo:** SIMS CUBA LBA. Marca, identidad visual y nombre final pendientes.

## Objetivo
Crear un simulador social de vida cubana con capacidades funcionales comparables a las que puedan verificarse de CubitaLife, pero con implementación independiente: código, mundo, personajes, arte, música, textos, interfaz y marca originales. Se estudian flujos y capacidades, no se copian recursos ni expresión protegida.

## Estado de investigación
- Una grabación de sesión autenticada en Chrome/Android del 26-11-2026 permitió auditar visualmente mapa de Camagüey, HUD, teléfono virtual y múltiples módulos. Ver [registro cronológico](evidence/observations/session-android-2026-11-26.md).
- La grabación muestra pantallas y textos, no transacciones completas. Movimiento, cámara efectiva, persistencia, economía real del juego y sincronización siguen pendientes.
- La portada y los términos oficiales se reconsultaron el 27-11-2026. Los términos siguen indicando última actualización 12-11-2026.
- El mayor vacío sigue siendo el comportamiento: onboarding/creación de personaje/spawn, controles, transiciones y resultados antes/después.
- El propietario debe aportar una nueva grabación de su sesión legítima para cerrar esos puntos. Ver [plan de captura](evidence/observations/next-session-capture-plan-2026-11-27.md).

## Arquitectura provisional
- Cliente: Godot 4.7.2 estable + GDScript como candidato; validar exportación Android y rendimiento en dispositivo real.
- Android: objetivo de publicación exige target API 36 desde el 31-08-2026. Debe probarse la combinación exacta de Godot, SDK y plantilla antes de fijarla.
- Backend piloto: Cloudflare Workers + Durable Objects/SQLite es un candidato; la persistencia global (D1, DO SQLite o PostgreSQL) no está decidida.
- Alternativa de servidor de juego: comparar Colyseus o Nakama self-hosted, que requieren una máquina y operación propias.
- Vercel WebSockets ya es GA desde 20-10-2026; las conexiones siguen sujetas a duración de Function y requieren reconexión/estado externo.
- Ningún tier gratuito se considera producción 24/7 ni capacidad ilimitada.

## Orden de trabajo
1. Cerrar evidencia de onboarding, spawn, movimiento/cámara y flujos no destructivos.
2. Convertir evidencia en matriz de paridad y GDD aprobado.
3. Probar exportación Android target API 36 y benchmark gráfico/térmico.
4. Hacer spike de backend y carga; medir latencia desde las regiones objetivo.
5. Construir un vertical slice original solo después de superar los gates.

## Estructura
- AGENTS.md: reglas de agentes.
- docs/00-project/: estado e índice.
- docs/01-reference-research/: investigación, inventario y matriz.
- docs/02-product-vision/: visión de producto.
- docs/03-game-design/: GDD y paridad.
- docs/04-technical-architecture/: arquitectura y ADR.
- docs/05-platforms/: Android y compilación.
- docs/06-production/: roadmap y backlog.
- docs/07-deployment/: hosting.
- docs/08-agent-workflow/: instrucciones para agentes.
- evidence/: fuentes y observaciones.
- decisions/: preguntas y riesgos.

## Evidencia
Cada hallazgo debe usar exactamente uno de estos estados principales:
- CONFIRMED: visible o ejecutado directamente en evidencia primaria; indicar si solo se confirmó UI.
- DOCUMENTED: declarado por fuente primaria oficial, sin prueba propia.
- HYPOTHESIS: inferencia aún no confirmada.
- PROPOSAL: diseño propio recomendado, sujeto a aprobación.
- PENDING: falta evidencia o decisión.

No convertir un botón visible en una acción probada. Registrar URL, fecha de consulta/publicación, procedencia, alcance y confianza en evidence/source-register.md.

## Propiedad intelectual y seguridad
No copiar código, assets, modelos, texturas, música, marca, textos expresivos ni composiciones identificables de CubitaLife. No guardar credenciales, tokens, datos privados ni grabaciones sin redactar en Git. No crear cuentas ni ejecutar compras, publicaciones o contactos de terceros para investigar.

## Licencia y decisiones sensibles
La licencia del código, la política de edad, marca, economía, monetización y pagos no están aprobadas. No decidirlas unilateralmente; ver LICENSE_DECISION.md y decisions/open-questions.md.
