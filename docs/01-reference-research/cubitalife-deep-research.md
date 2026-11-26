# Investigación profunda de CubitaLife — corte 26-11-2026

**Referencia:** https://cubitalife.com/  
**Términos:** https://cubitalife.com/terminos.html  
**Evidencia adicional:** recorrido de una sesión autenticada en Android/Chrome aportado por el propietario; [registro cronológico](../../evidence/observations/session-android-2026-11-26.md).  
**Método:** página pública, términos oficiales y revisión visual de grabación del usuario. No se inspeccionaron APIs privadas ni código fuente privado.

## 1. Descripción oficial
La portada presenta CubitaLife como un simulador social de vida en Cuba. Invita a buscar trabajo, decorar vivienda, hacer amigos, enamorarse y casarse con otras personas en línea. Menciona circunstancias iniciales diferentes. Afirma que la partida se guarda en la cuenta y sigue al usuario entre dispositivos.

**Estado:** DOCUMENTED por la descripción oficial.

## 2. Registro y requisitos
La portada muestra correo, nombre del personaje, contraseña y confirmación de 18 años o más. Los términos actualizados el 12-11-2026 declaran una cuenta por persona y un dispositivo a la vez.

**Estado:** CONFIRMED como UI / DOCUMENTED por términos. Validación, recuperación y seguridad de autenticación quedan PENDING.

## 3. Sesión móvil autenticada: hallazgo principal
La grabación muestra que CubitaLife es utilizable en Chrome móvil durante la sesión registrada y expone más subsistemas que los inferidos desde la portada. La partida mostraba Camagüey y una escena isométrica con edificios etiquetados, jugadores y lugares seleccionables. El teléfono virtual funciona como un hub de aplicaciones.

Sistemas visibles:
- Mundo/ciudad: mapa isométrico, lugares seleccionables, personajes y escenas interiores de establecimiento.
- HUD: cartera CUP, diamantes, ocupación/condición, energía, comida, humor y salud.
- Estado: localidad, clima, hora/fecha y estado del transporte.
- Misiones diarias y recompensa.
- Trabajo: empleos con requisitos, universidad, negocios, exterior, carpintería, mercado, inventario y anuncios.
- Casa: viviendas, muebles, comida y salud.
- Dinero: inversiones, sueldos, lotería, apuestas y subastas.
- Social: perfil, amigos, pareja, familia, grupos, reputación, prestigio, ranking y fiestas.
- Economía extendida: negocios con empleados, hotel, productos provinciales, almacenes, banco, mercado de relojes y valores de inversión.
- Viajes: zonas locales y ciudades cubanas; guagua, taxi o vehículo propio.
- Ciudad: vehículos, excursiones, periódico, tiempo, calle, gobierno, justicia, obras e historia.
- Música: conciertos, shows, estudio, radio y festival.
- CubaGram: publicaciones, ubicaciones, reacciones, comentarios, compartir, guardar y negocios etiquetados.
- Monetización/medios: diamantes, regalos de diamantes y anuncios en carteles con revisión.

**Estado:** CONFIRMED_UI para las pantallas recorridas en esa sesión; comportamiento completo NOT_TESTED. No se publican identificadores, saldos ni nombres de otros jugadores que aparecen en la grabación.

## 4. Observaciones sobre el mundo
La portada pública renderiza una escena de La Habana (Paseo del Prado/Malecón). La sesión real del usuario muestra Camagüey. Por tanto, las capturas públicas no bastan para afirmar que todos los jugadores inician en La Habana o que solo existe una ciudad. El mapa muestra establecimientos/servicios como gimnasio, discoteca, bodega, farmacia, paladar, biblioteca, teatro y parque, además de hogares/negocios. Se observa una fábrica de quesos como lugar interior seleccionable.

**No probado:** movimiento libre, navegación de cámara efectiva, colisiones, interacción con NPC, concurrencia, servidor de zona, latencia o transición completa entre lugares.

## 5. Teléfono como hub
El teléfono agrupa aplicaciones temáticas, buscador de apps, tarjeta de estado y misiones. Es un patrón estructural importante para la experiencia móvil. No debe copiarse el diseño visual exacto; la lección de producto es ofrecer un hub de subsistemas con navegación clara y acceso rápido.

## 6. Economía y profesiones
La interfaz muestra un sistema amplio:
- Empleo/carrera con buscador, requisitos de curso/reputación, turnos, ascensos y comparación de salarios por provincia.
- Universidad como sección de trabajo.
- Negocios propios, hotel, empleados, ingresos cobrables, expansión y cadenas.
- Carpintería y servicios entre jugadores mediante encargos.
- Mercado de productos provinciales e inventario comercial con capacidad, almacenes y espacio alquilado.
- Inversiones con cotización/variación/riesgo y opciones de posición.
- Banco con productos, transferencias, crédito y cuotas.
- Mercado de relojes y otros jugadores.
- Lotería, apuestas y subastas aparecen en el menú Dinero.

**No probado:** completar ninguna transacción ni fórmula económica. No tratar los valores visibles como una economía estable o universal.

## 7. Vivienda, necesidades y salud
La interfaz ofrece tipos de vivienda, vista 3D, alquiler y compra; muebles, paredes y acabados; comida para llevar; y acciones de salud como consultorio, dormir, comer, gimnasio y farmacia. Algunas fichas indican cambios en necesidades y costes.

**No probado:** adquirir o decorar vivienda, consumir comida, curar una enfermedad, cálculo de necesidad, tiempos de regeneración o guardado de acciones.

## 8. Familia y relaciones
Pantallas visibles para pareja, familia, hijos y adopción, con manutención y costes mostrados. La UI indica caminos para conocer personas en lugares sociales o desde la lista de amigos. Social también incluye perfil, grupos, reputación, prestigio, ranking y fiestas.

**No probado:** iniciar relación, adopción, crear familia ni transferir manutención.

## 9. Viajes, ciudad y entretenimiento
Viajar enumera zonas de Camagüey y varias ciudades del país, con elección de guagua, taxi o vehículo propio. Ciudad lista vehículos, excursiones, periódico, tiempo, calle, gobierno, justicia, obras e historia. Música lista conciertos, shows, estudio, radio y festivales. Exterior presenta progreso de viaje internacional y negocios fuera de Cuba.

**No probado:** comprar un viaje, completar una ruta, conducir, asistir a evento o abrir todos los submódulos.

## 10. CubaGram y comunidad
CubaGram muestra un feed con publicaciones por localización, reacciones, comentarios, compartir, guardar y negocios etiquetados. Los términos también mencionan chat, CubaGram y mensajes privados y exigen normas de convivencia.

**No probado:** publicar, enviar mensajes, comentar, reportar, bloquear, privacidad, filtrado o herramientas de moderación.

## 11. Términos y monetización oficiales
Los términos, actualizados el 12-11-2026, declaran:
- Acceso para mayores de 18 años; una cuenta por persona y un dispositivo a la vez.
- CUP, fulas, oro y monedas de juego son ficticias y no tienen valor real de canje.
- Diamantes comprables mediante Stripe; beneficios como energía infinita, necesidades llenas, viajes sin espera, VIP, cambio de imagen, coches exclusivos, anuncios en carteles y Remesa Express.
- La página limita el uso del CUP recibido por Remesa Express.
- Pagos, reembolsos y regalos; los datos de pago son procesados por Stripe.
- Guardado de correo, partida y publicaciones; opciones de borrado.
- Anuncios voluntarios de Google para energía en ciertos países.
- El servicio continúa en desarrollo y puede cambiar o interrumpirse.

La pantalla móvil mostró también métodos de pago locales/internacionales y una pantalla separada para comprar anuncios en carteles. No se ejecutó ninguna compra, pago o envío.

## 12. Fuentes secundarias
Un artículo de A Ver Qué Sale publicado el 15-11-2026 describe inicio aleatorio con provincia/dirección/condición social/dinero, remesas familiares, movilidad entre provincias y actividades ilegales con sanciones. Es una fuente secundaria: esos detalles **no quedan confirmados** por la sesión ni por los términos revisados. Mantenerlos como PENDING hasta evidencia primaria.

## 13. Motor, APIs y arquitectura privada
No se puede deducir de una grabación ni de la web pública qué motor, lenguaje, base de datos, proveedor de hosting, protocolo o diseño de servidor utiliza CubitaLife. No usar escaneo, extracción de API privada ni elusión de controles para intentar averiguarlo. Para SIMS CUBA LBA, validar nuestra propia arquitectura mediante prototipos y pruebas.

## 14. Conclusión para SIMS CUBA LBA
La referencia es un simulador social/económico con subsistemas interdependientes, no solo una escena 3D con chat. El orden de implementación recomendado pasa a ser:
1. Mundo móvil, avatar, cámara y localización.
2. Modelo de personaje/HUD, necesidades, billetera y misiones.
3. Hub de teléfono y módulos de casa/vida diaria.
4. Trabajo/formación, vivienda y economía básica.
5. Comercio/negocios/inventario/viajes.
6. Social/CubaGram y moderación antes de habilitar comunicación pública.
7. Entretenimiento, ciudad, marketplace y monetización solo después de aprobar alcance, edad, privacidad y equilibrio.

La app de destino sigue siendo Android instalable y táctil; que el sitio sea navegable en Chrome móvil no convierte una WebView en la decisión correcta.
