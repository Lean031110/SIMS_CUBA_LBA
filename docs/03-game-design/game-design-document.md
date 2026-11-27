# Game Design Document — borrador de preproducción

**Revisión:** 27-11-2026  
**Estado:** PROPOSAL. Este documento describe el diseño propio de SIMS CUBA LBA; no afirma conocer las mecánicas internas no probadas de CubitaLife.

## Fantasía principal
Crear y vivir una vida virtual en una Cuba contemporánea estilizada: recorrer espacios urbanos, gestionar rutinas y necesidades, progresar y construir relaciones en un mundo persistente.

## Pilares
1. Vida cotidiana con consecuencias comprensibles.
2. Mundo social con identidad local y seguridad.
3. Progresión basada en actividades y decisiones.
4. Cultura cubana representada con respeto y contenido original.
5. Sesiones móviles cómodas y tolerantes a conectividad inestable.
6. Economía ficticia transparente, auditable y protegida por servidor.

## Base de referencia observada

La sesión aportada el 26-11-2026 permite confirmar visualmente pantallas y módulos, no sus operaciones. El [inventario detallado](../01-reference-research/known-features-inventory.md) y el [catálogo funcional](../01-reference-research/cubitalife-gameplay-systems-catalog.md) registran el alcance exacto.

| Sistema de referencia | Estado de evidencia | Implicación de diseño para SIMS CUBA LBA |
|---|---|---|
| Mundo isométrico, calles, edificios y avatares | CONFIRMED como UI/escena visible | Diseñar barrio original navegable y puntos de interés propios |
| HUD, cartera CUP, diamantes y cuatro necesidades | CONFIRMED como UI visible | Probar HUD legible y atributos desacoplados; fórmulas propias pendientes |
| Teléfono virtual con launcher, búsqueda y categorías | CONFIRMED como UI visible | PROPOSAL: hub móvil para abrir subsistemas sin perder contexto |
| Trabajo, universidad y requisitos | CONFIRMED como pantallas/textos | Reglas de empleo, turnos, salario y progresión siguen PENDING |
| Vivienda, alquiler/compra y muebles | CONFIRMED como pantallas/textos | Sistema propio de propiedad/decoración requiere especificación |
| Negocios, mercado, inventario, banco e inversiones | CONFIRMED como pantallas/textos | Operaciones, saldos, límites y persistencia no probados |
| Comida, salud, descanso y gimnasio | CONFIRMED como pantallas/textos | Efectos y fórmulas no probados |
| Viajes, ciudad y transporte | CONFIRMED como pantallas/textos | Rutas, tarifas y tiempos no probados |
| Perfil, pareja, familia, grupos y CubaGram | CONFIRMED como pantallas/textos | Relaciones, publicaciones y privacidad no probadas |
| Chat y mensajes privados | Chat visible en portada; DM DOCUMENTED por términos | Envío, entrega, moderación y privacidad PENDING |
| Primer registro, personaje, spawn y tutorial | PENDING | No diseñar un flujo de paridad cerrado hasta capturar la primera entrada |
| Movimiento táctil, cámara efectiva y transiciones | PENDING | Gate de locomoción antes de fijar controles y mapa |

## Bucles propuestos
- Corto: entrar → revisar estado → elegir actividad → recibir resultado → actualizar estado.
- Medio: trabajar/estudiar → ganar recursos o conocimiento → desbloquear opciones.
- Largo: mejorar vivienda, habilidades y relaciones → explorar más zonas.

Estos bucles son PROPOSAL de diseño; no son descripción confirmada de los sistemas internos de CubitaLife.

## Vertical slice propuesto — no aprobado aún
1. Un barrio cubano original y compacto.
2. Un personaje original con controles táctiles.
3. Cámara, selección de un punto de interés y entrada/salida de un interior no transaccional.
4. HUD de prueba con estado de personaje y valores ficticios.
5. Una actividad sencilla que cambie un atributo de prueba con autoridad del servidor.
6. Pausa, reconexión y recuperación de snapshot.
7. Sin chat público, pagos, apuestas, marketplace ni transacciones entre usuarios en esta primera slice.

La vertical slice solo empieza cuando se superen los gates de evidencia de onboarding/locomoción, exportación Android API 36 y spike de backend. La propuesta no autoriza por sí sola decisiones de edad, marca, economía o monetización.

## Sistemas fuera del primer prototipo
- Chat público, DM y feed social abierto.
- Pagos reales, apuestas, transferencias y conversión de moneda.
- Familia/adopción y relaciones con consecuencias.
- Banco, crédito, inversiones y mercados entre jugadores.
- Negocios con empleados y economía persistente de varios usuarios.

## Reglas de diseño
- Todo valor económico se valida en servidor y se registra en un ledger.
- El cliente muestra snapshots; no decide saldo, recompensas ni inventario final.
- Las acciones con coste requieren confirmación y respuesta idempotente.
- Las funciones sociales requieren bloqueo, reporte, moderación, filtros y controles de privacidad antes de abrirse.
- La app debe degradarse con conexión lenta: caché de lectura, reintentos con backoff y recuperación sin duplicar operaciones.
- El contenido, mapas, edificios, personajes, interfaz y textos serán originales.

## Alcance bloqueado
No fijar fórmulas de necesidades, salarios, trabajos, estudios, viajes, relaciones, propiedades ni progresión social sin evidencia o aprobación explícita.
