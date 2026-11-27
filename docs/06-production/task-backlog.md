# Backlog de investigación y producción — revisión 27-11-2026

## P0 — cerrar evidencia y gates

- [x] R-01 Obtener evidencia de una sesión real en Android/Chrome y registrar HUD, mapa y módulos abiertos.
- [x] R-02 Inventariar visualmente el teléfono virtual y sus categorías.
- [x] R-03 Registrar pantallas de vivienda, trabajo, negocios, economía, salud, social, ciudad y viajes.
- [ ] R-04 Capturar onboarding, login seguro, personaje, primer spawn y tutorial sin resetear la cuenta.
- [ ] R-05 Verificar movimiento táctil, cámara, colisiones, selección de edificios y transiciones.
- [ ] R-06 Observar valores de necesidades en dos momentos y separar variación natural de causa.
- [ ] R-07 Profundizar empleo/universidad sin aceptar puestos ni pagar cursos.
- [ ] R-08 Explorar vivienda/muebles sin comprar ni cambiar titularidad.
- [ ] R-09 Documentar mercado/inventario/negocio sin ejecutar compra, venta, cobro o contratación.
- [ ] R-10 Revisar perfil, privacidad, CubaGram y chat sin publicar ni contactar jugadores.
- [ ] R-11 Verificar viajes y coste/tiempo real sin confirmar desplazamientos.
- [ ] R-12 Confirmar o descartar claims secundarios sobre spawn aleatorio, remesas periódicas y delitos/sanciones.
- [ ] R-13 Construir tabla de dependencia y prioridad para paridad v1.

## P1 — decisiones técnicas bloqueantes

- [ ] T-01 Exportar proyecto mínimo Godot 4.7.2 a APK con target API 36; inspeccionar manifiesto.
- [ ] T-02 Instalar y ejecutar APK en Android 16 real y un Android anterior.
- [ ] T-03 Benchmark de controles, FPS, RAM, temperatura, batería y tamaño de build en dispositivo modesto y medio.
- [ ] T-04 Spike Cloudflare Workers + DO WebSocket Hibernation y persistencia SQLite/D1.
- [ ] T-05 Comparar Colyseus o Nakama self-hosted para una zona autoritativa.
- [ ] T-06 Prueba de carga 20/50/100 clientes; medir p50/p95, mensajes, reconexión, errores y coste.
- [ ] T-07 Medir latencia desde redes que representen Cuba y probar pérdida/jitter.
- [ ] T-08 Definir política de backups, restore, exportación y presupuesto.

## Gates antes del vertical slice
- [ ] G-01 Evidencia de onboarding/primer spawn y locomoción suficiente para definir el bucle base.
- [ ] G-02 Godot/Android exporta con target API 36 y corre en dispositivo real.
- [ ] G-03 Backend elegido tras spike, reconexión y prueba de carga.
- [ ] G-04 GDD y paridad v1 revisados; decisiones de edad, licencia, marca y pagos siguen bajo aprobación separada.

## P2 — vertical slice original (bloqueado por gates)
- [ ] V-01 Menú y cuenta de prueba.
- [ ] V-02 Avatar/personaje original.
- [ ] V-03 Zona cubana original, mapa y locomoción táctil.
- [ ] V-04 HUD con necesidades/cartera/misiones de prueba, validado por servidor.
- [ ] V-05 Teléfono virtual con módulos desacoplados.
- [ ] V-06 Una actividad completa, medible y persistente.
- [ ] V-07 Controles de bloqueo/reporte y moderación antes de chat público.

## P3 — paridad por subsistemas
- [ ] P-01 Movimiento, mapa y lugares seleccionables.
- [ ] P-02 Necesidades, comida y salud.
- [ ] P-03 Trabajo, cursos y universidad.
- [ ] P-04 Vivienda, alquiler/compra y muebles.
- [ ] P-05 Negocios, empleados e inventario.
- [ ] P-06 Viajes, transporte y ciudad.
- [ ] P-07 Social, familia y CubaGram.
- [ ] P-08 Economía extendida: banco, mercado, inversión y otros sistemas.
- [ ] P-09 Música, eventos, anuncios y monetización (sujetos a aprobación legal/producto).

## P4 — release
- [ ] L-01 QA de dispositivos.
- [ ] L-02 Carga y coste por usuario.
- [ ] L-03 Seguridad y recuperación de backup.
- [ ] L-04 APK/AAB, políticas y publicación.

## Mejoras posteriores
- [ ] X-01 Más provincias y barrios con identidad local.
- [ ] X-02 Más profundidad profesional y de negocios.
- [ ] X-03 Accesibilidad y bajo consumo/datos.
- [ ] X-04 Eventos, accesibilidad, personalización y progresión ampliada.
