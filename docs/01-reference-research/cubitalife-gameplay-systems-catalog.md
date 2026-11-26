# Catálogo funcional observado en la sesión real

**Corte:** 26-11-2026  
**Base principal:** grabación de sesión autenticada en Android/Chrome aportada por el propietario; detalle cronológico en [evidencia de sesión](../../evidence/observations/session-android-2026-11-26.md).  
**Leyenda:** CONFIRMED_UI = pantalla abierta; OBSERVED_COPY = texto visible; NOT_TESTED = efecto no probado.

## 1. Mundo y personaje
| Subsistema | Elementos vistos | Estado |
|---|---|---|
| Mapa urbano | Camagüey isométrico, calles, manzanas, edificios, comercios y servicios etiquetados | CONFIRMED_UI |
| Puntos de interés | Fábrica de quesos, gimnasio, discoteca, bodega, farmacia, paladar, biblioteca, teatro, parque, casas del barrio y otros edificios | CONFIRMED_UI |
| Población | Avatares y etiquetas de jugadores en el mapa | CONFIRMED_UI |
| Escena interior/lugar | Fábrica de quesos con opción de salir | CONFIRMED_UI |
| Perfil HUD | Avatar, nombre, ubicación, ocupación/condición, cartera y diamantes | CONFIRMED_UI |
| Necesidades | Energía, comida, humor y salud con escala 0–100 | CONFIRMED_UI |
| Contexto | Clima, hora, fecha y estado del transporte | CONFIRMED_UI |

**No demostrado:** movimiento libre, interacción con NPC, colisiones, mapa persistente, densidad máxima o sincronización multijugador.

## 2. Teléfono
- Tarjeta de ciudad/clima y cartera/reputación.
- Misiones diarias con progreso, objetivo pendiente y recompensa.
- Búsqueda de aplicaciones.
- Lanzador: Apoyar, Diamantes, Comprar CUP, Rueda, Tutoriales, Avisos, Redes, Dinero, Social, Trabajo, Casa, Ciudad, Bolsa de negocios, Música, Relojes y Viajes.
- Dock con accesos de cámara, mensajes, banco y transporte.

## 3. Trabajo y formación
- **Empleos:** búsqueda de puestos; algunas ocupaciones requieren cursos y reputación.
- **Carrera:** ayuda sobre turnos y ascensos; comparar salarios por provincia.
- **Universidad:** icono presente en Trabajo; contenido no abierto.
- **Negocios:** gestión de pequeñas empresas, hoteles, contratación y gestión de empleados jugadores.
- **Carpintería:** encargar muebles a otros jugadores, listar trabajos, ver taller propio.
- **Exterior:** progresión de viajero, cupos y operaciones fuera de Cuba.
- **Mercado e inventario:** comercio de mercancía con procedencia provincial, compra por lotes, transporte, almacenes y alquiler de espacio.

**No demostrado:** aceptar un empleo, terminar un curso, cobrar salario, completar pedido, contratar/despedir, vender mercancía o crear una cadena.

## 4. Vivienda
- Tipos de inmuebles: casa, villa colonial con jardín, casa con piscina, mansión y gran mansión frente al mar.
- Vista previa 3D manipulable por arrastre.
- Alquiler estatal, invitación, cierre con llave y abandono.
- Precio de compra y cálculo de dinero faltante.
- Muebles y personalización visual: colores/acabados y paredes.
- Encargos de mobiliario a carpinteros jugadores.

**No demostrado:** comprar, alquilar, mudar, colocar muebles, permisos de visita, persistencia de decoración o titularidad real en servidor.

## 5. Dinero y economía
- **Dinero:** inversiones, sueldos, lotería, apuestas y subastas.
- **Inversiones:** instrumentos, precios actuales, variación 24h, riesgo y exposición del jugador; interfaz de operaciones long/short.
- **Banco:** productos/tarjetas, transferencias a amigos, crédito y cuotas diarias visibles.
- **Negocios:** ingresos acumulados/cobrables, empleados y expansión.
- **Mercado:** artículos procedentes de distintas provincias, precio de compra y precio de venta.
- **Relojes:** mercado de artículos entre jugadores con rareza y filtros.
- **Cartera:** CUP y diamantes.

Los valores numéricos visibles son muestras de una cuenta/sesión concreta y una cotización puntual; no deben convertirse en constantes de diseño. No se verificaron apuestas, compras, transferencias o rendimientos.

## 6. Necesidades y salud
- Comida para llevar: productos con precio y cambio de comida, energía y humor.
- Consultorio: curar enfermedades.
- Dormir: acción condicionada a estar en casa/cama y a tiempo de noche, con efecto de energía mostrado.
- Comer: platos distintos vinculados con salud.
- Gimnasio: consume energía y mejora salud/humor según el texto.
- Farmacia: medicamento con precio y efecto de salud.

**No demostrado:** fórmula de regeneración, curvas de deterioro, enfermedad real, cooldown, límites diarios o persistencia offline.

## 7. Relaciones y comunidad
- Perfil, amigos, pareja, familia, grupos, reputación, prestigio, ranking y fiestas.
- Pareja: pantalla de estado sentimental, rutas para conocer jugadores y formar relación.
- Familia: parentescos, hijos, manutención y adopción.
- CubaGram: feed con ubicaciones, texto, reacciones, comentarios, compartir, guardar, negocios etiquetados y pestañas sociales.
- La presencia de chat y mensajes privados también se menciona en términos oficiales.

**No demostrado:** envío de mensaje, seguimiento, bloqueo, privacidad de perfil, moderación, reportes, consentimiento y sincronización de relaciones.

## 8. Ciudad, viajes y entretenimiento
- Viajar: zonas locales, ciudades cubanas y elección de guagua, taxi o coche propio.
- Ciudad: vehículos, excursiones, periódico, tiempo, calle, gobierno, justicia, obras e historia.
- Música: conciertos, shows, estudio, radio y festivales; estado de artista, fama y seguidores.
- Anuncios: contratar espacio en carteles por ubicación y duración, con moderación/revisión.
- Exterior: viajes internacionales/progresión y negocios fuera del país.

**No demostrado:** ejecutar viaje, conducción, economía de transporte, eventos en vivo, publicar anuncios o aprobar anuncios.

## 9. Monetización y normas
La pantalla de diamantes muestra opciones de pago locales e internacionales y regalos de diamantes; no se hizo compra. La pantalla Anuncios ofrece ubicaciones/duración y revisión. Los términos oficiales especifican mayoría de 18 años, monedas virtuales sin valor de canje, diamantes de pago, Stripe, límites de uso, protección de datos y reglas comunitarias: https://cubitalife.com/terminos.html.

## 10. Implicaciones para SIMS CUBA LBA
1. No reducir el producto a avatar + chat + casa; la referencia presenta varios subsistemas económicos interconectados.
2. Diseñar el teléfono como hub de navegación accesible y táctil, con búsqueda y acceso rápido.
3. Tratar moneda, inventario, contratación, vivienda, viaje y relaciones como sistemas de servidor autoritativos.
4. Modelar datos observables por separado: necesidades, wallet, reputación, misiones, localización, ocupación.
5. Separar comercio entre jugadores, negocios propios, mercado entre provincias y monetización premium.
6. Moderación y privacidad son dependencias previas a redes, grupos, CubaGram y chat.
7. El MVP no necesita replicar todos los menús de golpe. La matriz de paridad debe priorizar flujos completos, seguros y medibles.
