# Investigación profunda de CubitaLife — corte 26-11-2026

**Referencia:** https://cubitalife.com/  
**Términos:** https://cubitalife.com/terminos.html  
**Método:** páginas públicas y render textual público. No se realizó una sesión autenticada ni se inspeccionaron APIs privadas.

## 1. Descripción oficial
La portada presenta CubitaLife como un simulador social de vida situado en Cuba. Invita a buscar trabajo, decorar una vivienda, hacer amigos, enamorarse y casarse con otras personas en línea. Menciona circunstancias iniciales diferentes, desde un solar hasta la élite. Afirma que el progreso se guarda en la cuenta y sigue al usuario entre dispositivos.

**Estado:** DOCUMENTED por la descripción oficial, no por una partida jugada.

## 2. Registro visible
La portada muestra correo, nombre de personaje, contraseña (mínimo de seis caracteres), confirmación de mayoría de edad y una acción para empezar la vida. También aparece una opción de entrar.

**Estado:** CONFIRMED como elementos visibles. Validación, recuperación, verificación de correo y seguridad quedan PENDING.

## 3. HUD y navegación visibles
El render público expone:
- Nombre de muestra “Carlos” (no es necesariamente un nombre inicial universal).
- Cartera y moneda CUP.
- Necesidades: Energía, Comida, Humor y Salud.
- Navegación: Explorar, Trabajo, Estudiar, Mi casa y Viajar por Cuba.
- Contexto de escena La Habana, con Paseo del Prado, Malecón y fachadas coloniales.
- Entrada “Escribe en la sala…” que sugiere un chat.
- Acciones rápidas: Mi celular, El barrio, Ir a casa y Comer.
- Controles de cámara: rotar, centrar/N y zoom −/+.

**Estado:** CONFIRMED como texto/control visible. No se ha probado qué hace cada botón.

## 4. Controles declarados
La ayuda oficial indica clic para caminar, Q/E para girar y rueda del ratón para zoom.

**Estado:** DOCUMENTED por la ayuda oficial; no se ejecutó en una partida.

## 5. Funciones adicionales de los términos
Los términos públicos, actualizados el 12-11-2026, mencionan:
- Juego orientado a mayores de 18 años.
- Una cuenta por persona y un dispositivo a la vez.
- Normas de convivencia para chat, CubaGram y mensajes privados.
- Monedas CUP, fulas y oro ficticias, sin valor de canje real.
- Diamantes comprables mediante Stripe y ventajas virtuales.
- Ventajas nombradas: energía infinita, rellenar necesidades, viajes sin espera, Pase VIP, cambio de imagen, carros exclusivos, anuncios en carteles y Remesa Express para CUP de juego.
- Anuncios voluntarios de Google en ciertos países a cambio de energía.
- Datos guardados: correo, partida y publicaciones; el documento indica que no venden datos y describe el borrado.
- El servicio dice que sigue en desarrollo y puede cambiar o sufrir interrupciones.

**Estado:** DOCUMENTED por los términos, no por prueba de transacciones.

## 6. Lo que no se puede inferir
No se conoce la mecánica real de trabajos, turnos, salarios, estudios, títulos, compra/decoración de viviendas, apps del celular, servicios del barrio, provincias, viajes, consumo de comida, frecuencia de necesidades, chat/grupos/voz, negocios, adopción, remesas entre jugadores ni capacidad concurrente. Tampoco se conocen motor, APIs, base de datos ni infraestructura privada.

Cualquier afirmación externa sobre estos sistemas debe seguir PENDING hasta confirmarse con evidencia primaria.

## 7. Limitaciones de acceso
El render público devolvió “Cargando el juego…” y “Vista previa no disponible en este dispositivo”. No había contexto de pestaña autenticado disponible. Esta investigación no equivale a ingeniería inversa interactiva completa.

Para continuar, usar capturas o grabaciones del propietario navegando su propia sesión legítima, con emails, mensajes, identificadores y datos personales ocultos. No compartir contraseñas ni códigos.

## 8. Conclusión
El esqueleto funcional de referencia incluye cuenta/personaje, HUD de necesidades, cartera, zona 3D, movimiento/cámara, explorar, trabajo, estudio, vivienda, viajes, chat y accesos contextuales. El comportamiento detallado debe esperar a la matriz de interacción y evidencia visual. La app objetivo será Android instalable y táctil, no una WebView asumida.
