# Evidencia S3 — SomnGuard: edge local sin sincronización

**Fecha de verificación:** 26 de noviembre de 2026 (America/Bogota)
**Resultado:** S3 sigue incompleta; esta evidencia registra una sesión real del portal y una ejecución local del edge.

## Evidencia visual

- `01-dashboard-sesion-iniciada-aportada-por-aprendiz.png`: copia de una captura proporcionada por Johan. Muestra una sesión abierta en el panel de usuario. Por sí sola no demuestra persistencia de datos ni la ejecución de un flujo completo.
- El computador dispone de una cámara integrada y puede ejecutar el software `somnguard-device` en Windows; no hace falta una Raspberry Pi dedicada para esta prueba de desarrollo. Referencias: [README del dispositivo](https://github.com/SomnGuard/somnguard-device/blob/main/README.md) y [ADR-010 de aprovisionamiento y reclamo](https://github.com/SomnGuard/somnguard-docs/blob/main/docs/05-architecture/decisions/records/ADR-010-provisioning-self-register.md).

## Observaciones de la sesión

- La sesión autenticada abrió `/user/dashboard`.
- Historial de eventos: cero eventos y estado vacío.
- Analítica: cero dispositivos asignados y cero eventos registrados.
- Monitoreo: el portal indicó que no hay dispositivos asignados y no mostró video.
- Cuenta: no hay dispositivo vinculado; la pantalla solicita un código de vinculación emitido por administración.
- El edge usó la cámara integrada en modo local, sin token ni conexión de telemetría. La ejecución y sus detecciones quedan descritas en `03-edge-local-run.md`.
- La instancia local tiene 0 tokens de aprovisionamiento activos y el usuario autenticado tiene rol `user`; el rol admin debe registrar/provisionar el dispositivo y entregar el código de reclamo por el flujo previsto.

## Contraste con PostgreSQL local

Consulta de conteos sin extraer correos, nombres, contraseñas ni tokens:

| Tabla/entidad | Registros |
|---|---:|
| `security.user` | 1 |
| `security.role` | 2 |
| `security.user_role` | 1 |
| `device_management.device` | 0 |
| `device_management.device_assignment` | 0 |
| `telemetry_service.event` | 0 |
| `telemetry_service.evidence` | 0 |

## Conclusión y paso requerido

El edge local detectó eventos reales del pipeline y los guardó en su cola SQLite offline, pero el portal y PostgreSQL siguen vacíos. Por ello no se verificó un recorrido de extremo a extremo hasta datos persistidos y visibles en el backend y no corresponde declarar S3 cerrada.

Para continuar, administración debe emitir un token de aprovisionamiento para el edge local o registrar el dispositivo manualmente, y entregar el código de reclamo. Después se debe vincular desde la cuenta de prueba, iniciar el edge en modo backend, generar una detección, comprobarla en el portal y contrastar su persistencia en PostgreSQL. No se sustituyó esa evidencia con datos simulados.
