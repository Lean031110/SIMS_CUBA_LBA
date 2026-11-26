# Especificación Android de paridad funcional

Los elementos observados se convierten en objetivos de producto. Los comportamientos no verificados quedan bloqueados para diseño detallado hasta contar con evidencia.

## 1. Entrada y cuenta
- Pantallas originales para crear cuenta, entrar, salir y recuperar acceso.
- Perfil/personaje según los flujos que se investiguen.
- Consentimiento y política de edad propios.
- Guardado en servidor y sincronización entre dispositivos autorizados.

Aceptación: una cuenta puede cerrar sesión, reinstalar y recuperar su partida sin duplicar progreso ni saldo.

## 2. Personaje y HUD
- Avatar 3D personalizable, identidad original.
- HUD con cartera/CUP y cuatro necesidades observadas: energía, comida, humor y salud.
- Indicadores legibles en móvil, escala y alto contraste.
- Fórmulas y efectos pendientes de evidencia o decisión propia.

Aceptación: indicadores sincronizados y valores manipulados rechazados por servidor.

## 3. Mundo 3D y controles
- Escena original de barrio cubano.
- Cámara tercera persona.
- Joystick táctil izquierdo, gestos de cámara y botón contextual de interacción.
- Límites de cámara, colisiones y recuperación al perder conexión.

Aceptación: movimiento fluido en dispositivo real sin teclado/ratón.

## 4. Navegación de vida
Secciones identificadas: Explorar, Trabajo, Estudiar, Mi casa y Viajar por Cuba. No inventar salarios, títulos, propiedad, decoración, rutas, cooldowns o resultados. La investigación debe definirlos. Una vertical slice puede usar reglas temporales propias etiquetadas como prototipo.

## 5. Social
Chat y funciones comunitarias se especificarán tras walkthrough. CubaGram y mensajes privados están documentados por los términos, pero pendientes de inspección. Bloqueo, silenciar, reportar, filtros y herramientas de moderación son obligatorios antes de abrir chat público.

## 6. Economía
CUP y otros saldos son virtuales. Ledger append-only, idempotencia y validación del servidor. No implementar pagos reales en el MVP.

## 7. Acciones rápidas
La portada muestra Mi celular, El barrio, Ir a casa y Comer. Diseñar iconos y navegación propios. Verificar el efecto de cada acción antes de darlo por equivalente.

## 8. Restricciones Android
App instalable nativa; pausa/reanudación; reconexión con backoff; snapshots autoritativos; presets gráficos; gestión térmica, batería y memoria; permisos mínimos.
