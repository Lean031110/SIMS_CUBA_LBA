# Inventario de funciones y estado de evidencia

**Corte:** 27-11-2026. Estado principal limitado a CONFIRMED, DOCUMENTED, HYPOTHESIS, PROPOSAL o PENDING.

| ID | Área | Hallazgo | Estado | Alcance / siguiente comprobación |
|---|---|---|---|---|
| REF-001 | Registro | Formulario público muestra correo, nombre de personaje, contraseña y confirmación 18+ | CONFIRMED | UI visible; no se envió |
| REF-002 | Login | Acción de entrar visible en portada | CONFIRMED | UI visible; login no probado |
| REF-003 | Validación de cuenta | Errores, verificación de correo, recuperación y cierre de sesión | PENDING | Capturar sin exponer credenciales |
| REF-004 | Creación de personaje | Flujo, avatar, apariencia, nombre, atributos iniciales | PENDING | No aparece en grabación |
| REF-005 | Spawn/tutorial | Ubicación inicial, selección aleatoria, tutorial y estado inicial | PENDING | No inferir desde una partida ya iniciada |
| REF-006 | Mundo | Mapa isométrico de Camagüey con edificios, puntos y avatares | CONFIRMED | Una sesión; no prueba población global |
| REF-007 | Interior | Escena de fábrica de quesos y control Salir visible | CONFIRMED | El botón/resultado de salida no se probó |
| REF-008 | Movimiento desktop | Ayuda pública declara clic para caminar | DOCUMENTED | Reproducir en partida |
| REF-009 | Movimiento táctil | Joystick, toque, arrastre o navegación táctil | PENDING | Grabar gesto y desplazamiento real |
| REF-010 | Cámara | Botones rotar/centrar/zoom visibles en portada | CONFIRMED | Comprobar efecto, límites y sensibilidad |
| REF-011 | Cámara móvil | Gestos de arrastre/pellizco en Android | PENDING | Probar por separado del movimiento |
| REF-012 | HUD | Nombre/ubicación/ocupación, cartera CUP, diamantes y cuatro barras | CONFIRMED | Una sesión y una cuenta |
| REF-013 | Necesidades | Energía, comida, humor y salud; escala visual 0–100 en catálogo | CONFIRMED | Fórmulas, tiempo y efectos PENDING |
| REF-014 | Contexto | Clima, hora/fecha, transporte y localidad en teléfono | CONFIRMED | Exactitud y actualización PENDING |
| REF-015 | Misiones | Misiones diarias con progreso y recompensa visible | CONFIRMED | Recompensa no reclamada |
| REF-016 | Teléfono | Launcher, búsqueda, categorías y dock de accesos | CONFIRMED | Navegación y persistencia pendientes |
| REF-017 | Trabajo | Empleos, requisitos de curso/reputación y ayuda de turnos/ascensos | CONFIRMED | No aceptar empleo ni cobrar |
| REF-018 | Universidad | Entrada/categoría visible en menú de Trabajo | CONFIRMED | Contenido, coste y resultados PENDING |
| REF-019 | Negocios | Pantallas de negocio/hotel, empleados, expansión e ingresos | CONFIRMED | Contratar/cobrar/abrir no probado |
| REF-020 | Vivienda | Catálogo, alquiler/compra, tipos y vista previa 3D | CONFIRMED | Sin alquiler ni compra ejecutados |
| REF-021 | Muebles | Catálogo de acabados, paredes y encargos | CONFIRMED | Colocar/guardar no probado |
| REF-022 | Comida/salud | Tienda, consulta, descanso, gimnasio y farmacia | CONFIRMED | Efectos/costes no probados |
| REF-023 | Mercado/inventario | Bienes por provincia, almacenes, transporte y lotes | CONFIRMED | Compra/venta/almacenamiento no probado |
| REF-024 | Economía | Inversiones, sueldos, lotería, apuestas, subastas y relojes | CONFIRMED | No se ejecutó operación |
| REF-025 | Banco | Productos, tarjetas, transferencias/crédito descritos en UI | CONFIRMED | No se transfirió ni pidió crédito |
| REF-026 | Viajes | Destinos locales/ciudades y guagua/taxi/vehículo propio | CONFIRMED | No se confirmó viaje |
| REF-027 | Social | Perfil, amigos, pareja, familia, grupos, reputación, ranking y fiestas | CONFIRMED | No se modificaron relaciones |
| REF-028 | Familia | Hijos/manutención y adopción visibles | CONFIRMED | No se adoptó ni se cambió familia |
| REF-029 | CubaGram | Feed, ubicación, reacciones, comentarios, compartir/guardar y perfil | CONFIRMED | No se publicó ni interactuó |
| REF-030 | Chat público | Entrada de sala visible en portada | CONFIRMED | Envío, canales y moderación PENDING |
| REF-031 | Mensajes privados | Términos mencionan mensajes privados | DOCUMENTED | UI, controles y entrega no probados |
| REF-032 | Ajustes/privacidad | Controles de privacidad, bloqueo, reporte y eliminación en UI | PENDING | Capturar ajustes sin tocar datos |
| REF-033 | Normas/edad | Términos declaran 18+, una cuenta/persona y un dispositivo activo | DOCUMENTED | No implica política para SIMS CUBA LBA |
| REF-034 | Monedas/pagos | Términos describen CUP/fulas/oro ficticios y diamantes/Stripe | DOCUMENTED | No se compró ni se verificó entrega |
| REF-035 | Datos/retención | Términos declaran correo, partida y publicaciones; opción de pedir borrado | DOCUMENTED | Proceso real de borrado no probado |
| REF-036 | Android | Sesión de juego en Chrome móvil Android | CONFIRMED | No demuestra app nativa |
| REF-037 | App nativa | APK, AAB o app Android propia de CubitaLife | PENDING | No se ha observado |
| REF-038 | Persistencia | Sitio declara que la partida sigue la cuenta entre dispositivos | DOCUMENTED | Probar recarga/cambio de dispositivo |
| REF-039 | Offline/reconexión | Juego durante pérdida de red, reanudación y conflicto de estado | PENDING | No probado |
| REF-040 | Motor/backend | Motor, API, protocolo, base de datos e infraestructura privada | PENDING | No inferir ni investigar tráfico privado |

## Reglas
- CONFIRMED para una pantalla no significa acción funcional confirmada.
- DOCUMENTED describe lo que declara una fuente primaria, no una garantía técnica.
- Los valores numéricos de una sesión no son constantes de diseño.
- Las mecánicas de fuentes secundarias sobre spawn aleatorio, remesas periódicas, delitos y sanciones siguen PENDING.
- No convertir filas en requisitos implementables hasta conocer precondición, acción, resultado, error y persistencia.
