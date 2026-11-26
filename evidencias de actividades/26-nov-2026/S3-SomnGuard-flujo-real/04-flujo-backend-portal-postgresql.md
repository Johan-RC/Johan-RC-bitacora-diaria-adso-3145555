# Evidencia S3 — recorrido edge, API, PostgreSQL y portal

**Fecha:** 26 de noviembre de 2026 (America/Bogota)
**Resultado:** flujo técnico de extremo a extremo comprobado en el entorno local.

## Criterio del plan

El correo que contiene el Acta 11 marca como obligatorio que los flujos principales de SomnGuard funcionen desde la pantalla hasta la base de datos, con datos guardados y visibles, sin datos inventados ni funciones simuladas (página 2). Esta verificación se hizo con el dispositivo edge local y los servicios SomnGuard reales del entorno de desarrollo.

## Recorrido realizado

1. En el inventario admin del portal se emitió un token de aprovisionamiento de un solo uso, ligado al serial del edge local.
2. `somnguard-device` inició con su cámara integrada y completó el auto-registro contra la API. El backend devolvió la identidad del dispositivo; no se guardó el token en `.env`, bitácora ni salida de evidencia.
3. El código de reclamo se usó en el formulario de vinculación del portal. El dispositivo quedó asignado a la cuenta local autenticada y el heartbeat pasó a estado activo.
4. El pipeline real de cámara generó eventos. La cola local previa sincronizó dos eventos offline; durante la ejecución del edge el registro mostró lotes confirmados de 19, 5 y 2 eventos, sin pendientes de reintento.
5. El historial de eventos del portal mostró 26 registros del dispositivo y permitió ver evidencia asociada en algunos eventos.
6. Se detuvo el proceso edge al terminar la comprobación.

Las etiquetas de eventos son resultados del clasificador de SomnGuard; esta evidencia no afirma un diagnóstico médico ni una condición de conducción.

## Verificación agregada de PostgreSQL

Consulta de solo lectura sobre las tablas del entorno local, sin extraer seriales, UUID, cuentas, claves ni contenido multimedia:

| Comprobación | Resultado |
|---|---:|
| Dispositivos registrados para esta prueba | 1 |
| Asignaciones activas | 1 |
| Eventos persistidos | 26 |
| Eventos sincronizados desde cola offline | 2 |
| Registros de evidencia asociados a eventos | 7 |
| Acciones de aprovisionamiento auditadas | 1 token usado y 1 reclamo |

El conteo de 26 eventos en PostgreSQL coincide con el total visible en el portal durante la verificación. Esto demuestra persistencia y lectura desde la interfaz, no una maqueta ni datos sintéticos.

## Protección de evidencia y alcance

- El token de aprovisionamiento fue de un solo uso y quedó consumido; el código de reclamo se usó para vincular la cuenta. No se incluyen credenciales ni identificadores del dispositivo en este archivo.
- Los 7 objetos de evidencia permanecen en el almacenamiento local de SomnGuard. No se copiaron al repositorio fotos, cuadros de cámara ni videos.
- La captura aportada previamente por el aprendiz muestra la sesión inicial, no este resultado final. La vista final se inspeccionó en el portal, pero no se archivó una nueva captura PNG; este archivo conserva los resultados agregados verificados y no usa una imagen sustitutiva.
- El aviso previo de almacenamiento al 97% y purga fallida queda fuera de S3 y requiere revisión dentro de S4/estabilidad.
- La evidencia acredita la prueba técnica local. No afirma que los instructores la hayan revisado o aceptado formalmente.

## Fuentes

- González Bonilla, J. A. (2026, 13 de noviembre). *Ficha 3145555 — Acta 11-2026: tercer plan de mejoramiento de Brayan Perdomo y Johan Steven Rodríguez* [Correo electrónico con Acta adjunta]. SENA. Copia PDF del correo, página 2.
- SomnGuard. (2026). *SomnGuard Device README*. GitHub. https://github.com/SomnGuard/somnguard-device/blob/main/README.md

**Declaración de uso de IA:** Codex asistió en el procedimiento local, la lectura agregada de resultados y la redacción de esta evidencia. El resultado se contrastó en el portal y PostgreSQL locales.
