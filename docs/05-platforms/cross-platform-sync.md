# Sincronización y continuidad de cuenta

Aunque Android sea la prioridad, separar el modelo de dominio del cliente para permitir un segundo cliente futuro. No implementar sync web hasta que exista demanda y API estable.

## Reglas
- Cuenta e identidad independientes del dispositivo.
- El servidor conserva el estado canónico.
- El cliente descarga snapshot y cambios posteriores.
- Operaciones económicas nunca se resuelven mediante merge del cliente.
- Versionado de esquemas y migraciones.
- Control de sesiones y dispositivos simultáneos según política propia.

El sitio de CubitaLife afirma que la partida se sincroniza entre dispositivos; no se ha probado esa afirmación en una sesión real.