# Estrategia de pruebas

## Cliente Godot
Unit tests de dominio, escenas smoke/headless, controles táctiles, pausa/resume, assets, memoria y export.

## Backend
Unit/integration, autorización, esquemas, idempotencia, concurrencia económica, reconexión, rate limits y migraciones.

## Android físico
Instalación limpia/upgrade, login, navegación, multitouch, llamadas/notificaciones entrantes, background, red intermitente, batería, thermal throttling y varios tamaños de pantalla.

## Multiplayer
1/2/10/20/50/100 clientes simulados según hardware y cuota; latencia P50/P95, jitter, paquetes, pérdida, reconexión y abuso.

## Economía y seguridad
Transacciones duplicadas, replay, saldo negativo, límites, permisos, bloqueo/reportes y fugas de datos.

## Evidencia
Cada test con PASS/FAIL/SKIPPED/NOT TESTED, versión, ambiente, commit y log seguro. No declarar PASS si no se ejecutó.