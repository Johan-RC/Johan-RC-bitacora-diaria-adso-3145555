# Evidencia S3 — SomnGuard: sesión sin dispositivo ni eventos

**Fecha de verificación:** 26 de noviembre de 2026 (America/Bogota)
**Resultado:** S3 sigue incompleta; esta evidencia registra el estado real observado.

## Evidencia visual

- `01-dashboard-sesion-iniciada-aportada-por-aprendiz.png`: copia de una captura proporcionada por Johan. Muestra una sesión abierta en el panel de usuario. Por sí sola no demuestra persistencia de datos ni la ejecución de un flujo completo.

## Observaciones de la sesión

- La sesión autenticada abrió `/user/dashboard`.
- Historial de eventos: cero eventos y estado vacío.
- Analítica: cero dispositivos asignados y cero eventos registrados.
- Monitoreo: el portal indicó que no hay dispositivos asignados y no mostró video.
- Cuenta: no hay dispositivo vinculado; la pantalla solicita un código de vinculación emitido por administración.
- No se activó cámara ni se generaron registros de prueba o eventos ficticios.

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

La sesión de usuario funciona, pero no se verificó un recorrido de extremo a extremo desde una acción real del portal hasta datos persistidos y visibles en PostgreSQL. Sin dispositivo vinculado ni evento, no corresponde declarar S3 cerrada.

Para continuar hace falta que administración asigne un dispositivo de prueba autorizado y proporcione un código de vinculación válido. Después se debe vincular desde la cuenta de prueba, ejecutar un flujo real que produzca un evento, comprobarlo en el portal y contrastar su persistencia en PostgreSQL. No se sustituyó esa evidencia con datos simulados.
