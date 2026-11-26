# Inventario de funciones y estado de evidencia

| ID | Área | Evidencia actual | Estado | Próxima comprobación |
|---|---|---|---|---|
| REF-001 | Crear cuenta | Correo, nombre, contraseña y check 18+ visibles en portada | CONFIRMED (UI) | Validaciones, recuperación y errores |
| REF-002 | Entrar | Acción visible en portada | CONFIRMED (UI) | Flujo de sesión |
| REF-003 | Guardado de partida | La portada afirma que sigue la cuenta entre dispositivos | DOCUMENTED | Prueba autorizada en dos dispositivos |
| REF-004 | Cartera | CUP/diamantes en HUD; tarjeta cartera/reputación | CONFIRMED (UI) | Ledger e historial |
| REF-005 | Necesidades | Energía, comida, humor y salud con escala 0–100 | CONFIRMED (UI) | Fórmulas, evolución y efectos |
| REF-006 | Mundo 3D | Escena isométrica, edificios etiquetados, avatares y puntos de interés en Camagüey | CONFIRMED (UI) | Movimiento, colisiones e interacción |
| REF-007 | Entrar/salir de lugar | Tarjeta de entrada a fábrica y botón salir dentro de lugar | CONFIRMED (UI) | Probar transición y persistencia |
| REF-008 | Trabajo / empleo | Buscador y tarjetas con requisitos de curso/reputación | CONFIRMED (UI) | Aceptación de puesto, turnos y pago |
| REF-009 | Estudiar / universidad | Icono Universidad en menú Trabajo | CONFIRMED (UI) | Cursos, costes y resultados |
| REF-010 | Viviendas | Catálogo, vista 3D, alquiler y compra | CONFIRMED (UI) | Compra, contrato, visitas y decoración |
| REF-011 | Muebles | Catálogo, paredes y acabados; carpintería de encargos | CONFIRMED (UI) | Colocación, pedido y entrega |
| REF-012 | Viajar | Pantalla con ciudades, zonas locales y medios de transporte | CONFIRMED (UI) | Costes, tiempos y transición real |
| REF-013 | Social | Perfil, amigos, pareja, familia, grupos, reputación, prestigio, ranking y fiestas | CONFIRMED (UI) | Flujos y controles de seguridad |
| REF-014 | Chat | Portada muestra input de sala; términos mencionan mensajes privados | DOCUMENTED / UI | Envío, canales, bloqueo y moderación |
| REF-015 | CubaGram | Feed con posts, ubicación, reacciones, comentarios, compartir, guardar y negocio | CONFIRMED (UI) | Publicar, privacidad y reportes |
| REF-016 | Mi celular | Lanzador de módulos y búsqueda visibles y recorridos | CONFIRMED (UI) | Efecto de cada app |
| REF-017 | Casa/vida diaria | Vivienda, muebles, comida y salud en un mismo grupo | CONFIRMED (UI) | Acciones transaccionales |
| REF-018 | Comer / comida | Catálogo de platos con precio y efectos indicados | CONFIRMED (UI) | Compra, consumo y recuperación |
| REF-019 | Salud | Consultorio, dormir, comer, gimnasio y farmacia | CONFIRMED (UI) | Fórmulas y reglas completas |
| REF-020 | Economía | Inversiones, salarios, lotería, apuestas y subastas | CONFIRMED (UI) | Leer flujos sin ejecutar operaciones |
| REF-021 | Inversiones | Activos, cotización, variación, riesgo y opciones long/short | CONFIRMED (UI) | Operaciones, liquidación y riesgo |
| REF-022 | Banco | Productos/tarjetas, transferencias, crédito y cuotas | CONFIRMED (UI) | Reglas/operaciones, sin transferir |
| REF-023 | Negocios | Gestión, hotel, negocios propios, ingresos y empleados | CONFIRMED (UI) | Apertura, cobro, contratación |
| REF-024 | Mercado e inventario | Mercancías provinciales, compra por lotes, almacenes y espacio alquilado | CONFIRMED (UI) | Compra/venta/almacenamiento |
| REF-025 | Exterior | Categoría de viajero, cupos/divisas y negocios en otros países | CONFIRMED (UI) | Requisitos y viaje real |
| REF-026 | Carpintería | Encargos a carpinteros jugadores y taller propio | CONFIRMED (UI) | Pedido y entrega |
| REF-027 | Ciudad | Vehículos, excursiones, periódico, tiempo, calle, gobierno, justicia, obras e historia | CONFIRMED (UI) | Abrir y probar submódulos |
| REF-028 | Música | Artista, seguidores, fama, conciertos, shows, estudio, radio y festival | CONFIRMED (UI) | Curso/evento y progresión |
| REF-029 | Relojes | Mercado entre jugadores, rarezas, filtros y precios | CONFIRMED (UI) | Compra/venta y custodia |
| REF-030 | Anuncios | Carteles por ubicación y duración, precio en diamantes y revisión | CONFIRMED (UI) | Envío y moderación |
| REF-031 | Misiones | Tarjeta diaria con progreso y recompensa | CONFIRMED (UI) | Ciclo de reinicio y reclamación |
| REF-032 | Transporte | Estado del transporte y accesos de movilidad visibles | CONFIRMED (UI) | Rutas, tarifas y movimiento |
| REF-033 | Reputación | Campo mostrado en tarjeta de cartera | CONFIRMED (UI) | Cómo se gana/pierde |
| REF-034 | Diamantes y ventajas | Pantalla de compra/regalo; términos describen ventajas premium | CONFIRMED (UI) / DOCUMENTED | Disponibilidad por región y concesión |
| REF-035 | Pagos | Pantalla muestra métodos; términos describen Stripe y reembolsos | DOCUMENTED / UI | No realizar compras para investigar |
| REF-036 | Anuncios recompensados | Términos mencionan energía por anuncios en ciertos países | DOCUMENTED | Países, consentimiento y proveedor |
| REF-037 | Cámara/movimiento | Controles públicos declarados; cámara visible en portada | DOCUMENTED / UI | Probar gestos y controles en mundo |
| REF-038 | Música/fiestas | Menús y categorías abiertos | CONFIRMED (UI) | Eventos y socialización |
| REF-039 | Edad y convivencia | Términos: 18+, una cuenta/persona, un dispositivo a la vez, normas | DOCUMENTED | Diseñar política propia de producto |
| REF-040 | Familia, adopción y manutención | Pantalla de familia muestra adopción, hijos y costes | CONFIRMED (UI) | Flujo completo y balance |
| REF-041 | Motor/backend | Sin evidencia primaria | PENDING | No adivinar ni copiar infraestructura |

### Reglas de lectura
- La evidencia de sesión prueba que una pantalla se mostró y pudo abrirse en esa cuenta; no que todos los usuarios tengan acceso idéntico.
- CONFIRMED (UI) no significa operación completada.
- Los importes, precios, cotizaciones y límites observados son datos variables o de cuenta; no son constantes de SIMS CUBA LBA.
- Afirmaciones de prensa no verificadas en la sesión se mantienen como SECONDARY_CLAIM / PENDING.
