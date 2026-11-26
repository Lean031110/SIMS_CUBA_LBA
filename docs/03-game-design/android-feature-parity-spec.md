# Especificación Android de paridad funcional

La base de referencia incluye una sesión real con múltiples pantallas y sistemas. La paridad se definirá por **capacidades y flujos**, nunca copiando código, arte, marca, textos expresivos o composición visual exacta. CONFIRMED_UI indica que una pantalla se observó abierta; los efectos no probados no deben transformarse en requisitos cerrados.

## 1. Entrada, cuenta y personaje
- Registro, acceso, perfil y guardado de progreso con identidad y UX originales.
- Política de edad, privacidad, bloqueo y seguridad propias.
- Un personaje con localización, ocupación/condición, atributos, cartera y reputación.
- Guardado y sincronización de partida con servidor autoritativo.

Aceptación: recuperar partida de prueba sin duplicar progreso ni saldo; todas las mutaciones sensibles verificadas en servidor.

## 2. Mundo, mapa y HUD
- Mundo 3D isométrico/original con barrios, calles, edificios/puntos de interés y presencia de otros jugadores.
- Entradas/salidas de lugares con transiciones controladas.
- HUD con energía, comida, humor y salud; cartera, identidad/ocupación y estado contextual.
- Capas de clima, hora, fecha, transporte, misiones y localización si se aprueban en alcance.

Aceptación: selección de punto, navegación y colisiones comprobadas; render estable en dispositivo objetivo; HUD accesible y sincronizado.

## 3. Teléfono como hub
- Lanzador de aplicaciones temáticas con búsqueda.
- Categorías separadas para Casa, Trabajo, Social, Dinero, Ciudad, Viajes y entretenimiento.
- Dock/context actions para las tareas frecuentes.
- Navegación entre módulos que preserve estado y permita volver al mundo.

Aceptación: módulos desacoplados, deep links internos y retorno seguro al juego sin perder selección.

## 4. Necesidades, comida y salud
- Subsistemas para energía, comida, humor y salud.
- Catálogo de comida con coste y efectos.
- Descanso, consulta, gimnasio y farmacia como posibilidades a validar.
- Toda fórmula, precio, cooldown y regla de progresión queda por determinar o decidir como regla propia.

Aceptación: reglas documentadas, balanceadas y probadas; servidor valida consumo y cambios.

## 5. Vivienda y muebles
- Catálogo con alquiler/compra, tipos de inmueble, visitas y privacidad.
- Vista previa 3D de interiores y personalización de muebles/acabados.
- Encargos/servicios entre jugadores como fase posterior.

Aceptación: propiedad/alquiler, permisos, colocación y decoración persisten y no permiten duplicar objetos.

## 6. Trabajo, estudio y negocios
- Catálogo de empleo con requisitos, cursos y progresión.
- Universidad/cursos; salarios, turnos y ascensos cuando se verifiquen.
- Negocios con ingresos, empleados, contratación y expansión.
- Oficios/servicios realizados por jugadores, como carpintería, en una fase de comercio social.

Aceptación: una actividad profesional completa con requisito, acción, resultado, pago/XP, persistencia y errores reproducibles.

## 7. Comercio, inventario y economía
- Mercado de artículos por procedencia, precio y compraventa.
- Inventario personal, transporte, almacenes y espacio de almacenamiento.
- Banco, inversiones y marketplace entre jugadores quedan fuera del MVP hasta aprobar riesgo/alcance.
- Ledger append-only, idempotencia y validación del servidor; CUP y divisas serán monedas ficticias sin conexión a valor real en la primera versión.

Aceptación: transacciones atómicas, sin duplicación, con historial auditable y pruebas de concurrencia.

## 8. Viajes y ciudad
- Zonas locales y destinos/provincias, medios de transporte y costes/tiempos propios.
- Submódulos de ciudad (noticias, clima, excursiones, vehículos, cultura y servicios) solo tras validar prioridad.
- Viajes entre zonas con estado persistente y reconexión.

Aceptación: ruta, coste, llegada y telemetría coherentes en servidor.

## 9. Social y comunidad
- Perfil, amigos, grupos, pareja/familia y feed original.
- Chat, mensajes privados y publicaciones requieren bloqueo, reporte, moderación, filtros, límites anti-spam y controles de privacidad antes de abrirlos.
- No se usarán handles ni publicaciones de CubitaLife; identidades y contenido de SIMS CUBA LBA serán propios.

Aceptación: flujos de privacidad y moderación probados con cuentas ficticias antes de habilitar comunicación pública.

## 10. Entretenimiento y monetización
- Música/eventos y otros mercados lúdicos son candidatas a fases posteriores.
- No implementar pagos reales, apuestas con dinero real ni conversión de moneda virtual a dinero real en el MVP.
- Cualquier monetización requerirá revisión legal, políticas de edad, países, reembolsos y protección de datos.

## 11. Restricciones Android
App instalable nativa; pausa/reanudación; reconexión con backoff; snapshots autoritativos; presets gráficos; gestión térmica, batería y memoria; permisos mínimos. Godot 4.x + GDScript permanece como decisión provisional hasta un benchmark real.
