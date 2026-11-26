# Ejecución local de SomnGuard Device

**Fecha:** 26 de noviembre de 2026 (America/Bogota)
**Repositorio:** [`SomnGuard/somnguard-device`](https://github.com/SomnGuard/somnguard-device) (`main`)
**Equipo:** Windows con cámara integrada. El usuario autorizó su uso para esta prueba.

## Preparación y ejecución

- Se instaló Python 3.11.9, se creó `.venv`, se instalaron las dependencias `.[stream]` y se descargaron los modelos indicados por el README. `.env` se copió desde `.env.example`; no contiene token de aprovisionamiento.
- El edge inició en modo local: cámara 1280×720 a 30 fps, modelos `face` y `phone` cargados y estado `ACTIVO`. El registro indicó expresamente que operaba sin credenciales ni token de aprovisionamiento.
- Salida relevante del proceso: `Cámara inicializada`, `Pipeline visión activo`, `Dispositivo en modo local (sin credenciales ni provision token)` e `Inicializado ... (estado=ACTIVO, backend=local)`.
- El pipeline registró EV-SOM-01 (clasificado por el software como parpadeo lento de 0,7 s) y EV-SYS-02 (campo visual obstruido a los 5 s). No se afirma que la primera detección sea un diagnóstico de somnolencia.
- El proceso también avisó `Almacenamiento al 97% (>90%): AS-09 + purga FAILED/evidencia 7d`; esta advertencia quedó sin diagnosticar y debe revisarse antes de considerar estable la prueba.
- La cola local `data/db/somnguard_local.db`, tabla `pending_events`, contiene 2 filas en estado `PENDING`: una EV-SOM-01 y una EV-SYS-02. La captura se detuvo con Ctrl+C y el proceso registró `Dispositivo apagado`.
- PostgreSQL, tras la ejecución: 0 dispositivos, 0 asignaciones, 0 eventos y 0 evidencias. Los eventos permanecen locales y no aparecen en el portal.

## Alcance de la evidencia

Esto demuestra que este computador puede funcionar como edge de desarrollo y que el pipeline guarda detecciones localmente. No demuestra sincronización edge→API→PostgreSQL→portal. El flujo backend requiere un token de aprovisionamiento emitido por admin o un alta manual de admin, y luego el reclamo/asignación del dispositivo.

No se copiaron imágenes ni video de la cámara a la bitácora.
