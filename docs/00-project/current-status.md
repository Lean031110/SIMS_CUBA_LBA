# Estado actual del proyecto

**Corte:** 26-11-2026  
**Fase:** 0 — investigación y preproducción  
**Implementación:** no iniciada  
**Plataforma objetivo:** aplicación Android instalable; APK para QA y AAB cuando corresponda a distribución.

## Qué se ha hecho
- Repositorio público preparado con estructura de investigación, diseño, arquitectura, producción y agentes.
- Inspección de la portada y términos oficiales de CubitaLife.
- Revisión de una grabación de sesión autenticada aportada por el propietario en Android/Chrome.
- Documentación de un mapa urbano isométrico de Camagüey, avatar/HUD, necesidades, cartera, misiones y teléfono virtual.
- Apertura visual de pantallas de trabajo, vivienda, muebles, negocios, mercado, inventario, inversiones, banco, salud, comida, pareja/familia, viajes, ciudad, música, relojes, anuncios y CubaGram.
- Separación explícita entre pantalla observada y acción/operación no probada.
- Registro de afirmaciones secundarias no verificadas como preguntas pendientes.
- Investigación inicial de WebSockets y opciones gratuitas de Vercel, Cloudflare, Render y Supabase.

## Qué se ha verificado
- La experiencia web se mostró funcionando en Chrome móvil durante la grabación aportada.
- El mundo de esa sesión estaba en Camagüey; la portada pública también puede mostrar La Habana.
- La interfaz contiene cuatro necesidades: energía, comida, humor y salud.
- El teléfono actúa como hub de múltiples subsistemas de juego.
- Hay pantallas dedicadas a profesión/economía, vivienda/vida diaria, social/familia, viajes/ciudad y entretenimiento.
- Los detalles de pantallas y textos están registrados en evidence/observations/session-android-2026-11-26.md.

## Qué NO se ha verificado
- No se probaron movimientos, colisiones, cámara interactiva ni capacidad concurrente.
- No se completaron compras, ventas, inversiones, apuestas, transferencias, contrataciones, adopciones, viajes o publicaciones.
- No se probó el efecto de botones, cálculos económicos, ciclos de necesidades, persistencia, sincronización o reconexión.
- No se inspeccionaron APIs, código fuente privado, motor, base de datos ni infraestructura de CubitaLife.
- No se comprobó una app Android nativa; el vídeo muestra Chrome móvil.
- No hay cliente, servidor ni APK implementados.

## Próximos hitos
1. Completar walkthrough seguro de movimiento/edificios y transiciones.
2. Verificar ciclos de necesidades, empleo/formación, vivienda, compra/venta y viajes mediante observación antes/después; no gastar saldos ni publicar sin autorización.
3. Cerrar matriz de paridad v1 y GDD Android por subsistema.
4. Validar ADR de motor y backend mediante prototipos.
5. Crear prototipo local de avatar, cámara, controles táctiles y zona original.
6. Añadir identidad, persistencia y primera conexión multijugador.
7. Implementar la línea base de capacidades priorizadas antes de mejoras propias.

## Bloqueos / límites
- La inspección se basa en una sesión/una cuenta; la disponibilidad puede variar entre jugadores.
- El juego declara ser para mayores de 18 años; SIMS CUBA LBA necesita definir su propia política de edad y seguridad.
- La política de privacidad, moderación, marca y licencia siguen pendientes.
- La grabación original no se publica en Git porque contiene identificadores del jugador y nombres de terceros.
