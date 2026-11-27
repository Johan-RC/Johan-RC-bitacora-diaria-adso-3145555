# Cuadro maestro de actividades y evidencias

**Aprendiz:** Johan Steven Rodriguez Charry  
**Ficha:** ADSO-3145555  
**Periodo del plan:** 14 de noviembre al 4 de diciembre de 2026  
**Entrega y sustentación:** 5 de diciembre de 2026  
**Corte de este estado:** 26 de noviembre de 2026

## Cómo usar este cuadro

Este documento reúne las actividades que corresponden a Johan según el Acta 11-2026 y el correo del instructor. Sirve como índice para preparar las entradas diarias y enlazar evidencia; no reemplaza los archivos `AAAA-MM-DD.md` ni autoriza a declarar trabajo que no se realizó.

Los documentos fuente no asignan una tarea diferente a cada día. La distribución diaria debe reflejar trabajo real y se puede ajustar con el instructor. Las fechas de control indicadas abajo son las propuestas del correo/Acta, sujetas a confirmación.

**Conteo del Acta:** 25 ítems para Johan (8 P-J, 11 compartidos de SomnGuard y 6 individuales) y 24 para Brayan (7 P-B, los mismos 11 de SomnGuard y 6 individuales).

**Estado del trabajo de Johan al 26/11:** 3 ítems (S1–S3) tienen evidencia técnica reunida, pero todavía les falta su validación/demostración formal; 7 están en curso o parcialmente avanzados (P-J4–P-J7, S4, I1 e I2); 15 siguen sin cierre o requieren validación (P-J1–P-J3, P-J8, S5–S11 e I3–I6). Por tanto, no hay todavía un ítem confirmado como aceptación final por los instructores.

- Cada ítem se evalúa como **CUMPLE** o **NO CUMPLE**; no hay estado parcial para la evaluación final.
- Los ítems marcados **(O)** son obligatorios. Para los demás se requiere al menos el 80% del bloque correspondiente.
- Para cerrar un resultado: evidencia en el repositorio mediante PR desde la cuenta del aprendiz hacia `develop`, CI en verde, dos aprobaciones de compañeros que no sean coautores y pruebas alineadas con los criterios.
- Mantener los límites entre evidencia del PDF, trabajo realizado y propuesta de organización. No convertir una fecha sugerida en requisito oficial.

## Estado de recuperación de los bloques 18 y 19

Este es un estado operativo de las fechas de trabajo acordadas; la recuperación se realizó el 23, 25 y 26 de noviembre, no en las fechas originales.

| Bloque | Estado actual | Pendiente para el cierre formal |
|---|---|---|
| 18 de noviembre | **Completado parcialmente — a la espera de revisión.** P-J4/P-J5, S1 y S2 tienen trabajo técnico y evidencia registrados. El CI #75 del PR #49 está en verde. | Revisión técnica del STRIDE; revisiones/aprobaciones válidas e integración del PR #49 en `develop`. Confirmar con los instructores si el video de S1 sustituye la sustentación en vivo; validar formalmente la evidencia S2. |
| 19 de noviembre | **Completado parcialmente — a la espera de revisión.** P-J6 tiene CI #74 en verde; S3 está probado técnicamente y su informe y capturas están publicados. | Revisiones/aprobaciones válidas e integración del PR #50 en `develop`; respuesta de los instructores sobre la evidencia S3. |

## A. Proyecto design-software de Johan

| Ítem | Actividad del Acta | Evidencia requerida | Obligatorio | Estado verificado al corte |
|---|---|---|---|---|
| P-J1 | Fusionar web-shell PR #29 en `develop`. | PR fusionado, CI verde y dos aprobaciones de compañeros no coautores. | Sí (O) | Revalidar el PR #29 y las aprobaciones antes del próximo control. |
| P-J2 | Fusionar design-system PR #10 en `develop`. | PR fusionado, CI verde y dos aprobaciones válidas. | Sí (O) | Revalidar el PR #10 y las aprobaciones antes del próximo control. |
| P-J3 | Fusionar frontend-platform PR #12 en `develop`. | PR fusionado, CI verde y dos aprobaciones válidas. | Sí (O) | Revalidar el PR #12 y las aprobaciones antes del próximo control. |
| P-J4 | Medir y registrar en `develop` los Core Web Vitals de web-shell: LCP, INP y CLS. | Informe con tres corridas, valores, comando reproducible y PR fusionado en `develop`. | No | Trabajo técnico y CI #75 completados en PR #49. El remote es simulado, no producción. **Completado parcialmente:** revisores solicitados, sin revisiones enviadas; pendientes validaciones/aprobaciones requeridas e integración en `develop`. |
| P-J5 | Elaborar el modelo de amenazas STRIDE de la federación y dejarlo en `develop`. | Documento con amenazas, mitigaciones y responsables, validado técnicamente y fusionado en `develop`. | No | Borrador STRIDE actualizado y CI #75 en PR #49; commit `044d9b5`. Revisión estática propia actualizada el 26/11; no sustituye la validación de responsables. **Completado parcialmente:** pendiente validación independiente, revisiones/aprobaciones requeridas e integración en `develop`. |
| P-J6 | Activar Content-Security-Policy y comprobar que una prueba automatizada falla si se elimina. | Política activa, prueba de regresión y ejecución visible en CI. | No | PR #50 abierto hacia `develop`; commit `3c55ee9` firmado y CI #74 exitoso. **Completado parcialmente:** revisores solicitados, sin revisiones enviadas; pendientes aprobaciones e integración en `develop`. Evidencia en la bitácora del 26/11. |
| P-J7 | Ejecutar regresión visual y presupuesto de tamaño. | Pruebas conectadas al CI y corrida verde con resultados reproducibles. | No | En curso desde 26/11 en `recovery/2026-11-26-pj7-visual-budget`; commit firmado `b3ac09c`, [PR #51](https://github.com/code-sena/design-software-web-shell/pull/51) abierto hacia `develop`, CI #76 en ejecución y revisiones solicitadas a `ariel5253`, `cjsarasty456` y `javierpintod`. Build, presupuesto, tipos E2E, lint focalizado y prueba visual local pasan. Evidencia en `evidencias de actividades/26-nov-2026/P-J7-regresion-visual-presupuesto/`. |
| P-J8 | Explicar por escrito los cuatro archivos de actividades idénticos detectados en el caso SomnGuard. | Informe de autoría sustentado con evidencia y explicación en vivo de un caso elegido por el instructor. | Sí (O) | Verificar que el informe esté entregado y que la sustentación quede pendiente/realizada según evidencia. |

## B. Proyecto SomnGuard compartido

| Ítem | Actividad del Acta | Evidencia requerida | Obligatorio | Estado verificado al corte |
|---|---|---|---|---|
| S1 | Levantar el sistema desde cero usando únicamente el manual de instalación y `.env.example`, sin cambiar código. | Procedimiento reproducible y demostración en vivo ante los instructores. | Sí (O) | **Completada técnicamente; verificación formal pendiente.** README, cinco capturas revisadas y video en `evidencias de actividades/18-nov-2026/S1-SomnGuard-arranque-desde-cero-2026-11-25-final/`. Muestran PostgreSQL saludable, 92 changesets, MailHog/S3Mock, API `/actuator/health` UP y portal HTTP 200. Falta demostrarlo o acordar con instructores si el video reemplaza la sustentación en vivo. |
| S2 | Ingresar con cada rol declarado usando usuarios de prueba documentados. | Usuarios de prueba documentados y evidencia de acceso para cada rol. | Sí (O) | **Completada técnicamente; verificación formal pendiente.** README, tres capturas revisadas y video en `evidencias de actividades/18-nov-2026/S2-SomnGuard-roles-admin-user-2026-11-25-final/`: dos cuentas sintéticas verificadas en MailHog local; admin obtuvo 200 y user 403 en `/api/v1/users`. El rol admin se asignó solo en una base temporal aislada; no se guardaron contraseñas ni tokens. Falta validación formal. |
| S3 | Verificar los flujos principales desde la pantalla hasta la base de datos. | Recorrido con datos guardados y visibles, sin datos inventados ni funciones simuladas. | Sí (O) | **Completada técnicamente; revisión pendiente.** Recorrido local de aprovisionamiento y reclamo desde la UI; cámara integrada → edge → API → PostgreSQL → portal. Historial de 26 eventos; PostgreSQL confirmó 1 dispositivo, 1 asignación activa, 26 eventos (2 sincronizados offline) y 7 registros de evidencia. Capturas 05–07 y el informe están publicados en `evidencias de actividades/26-nov-2026/S3-SomnGuard-flujo-real/`. |
| S4 | Comprobar estabilidad ante errores y caídas parciales. | Pruebas de token inválido (401), petición mala (400 sin trazas), listas vacías, rutas protegidas y servicio caído sin tumbar los demás. | No | **En curso (26/11):** pasan pruebas dirigidas para token mal formado (401), petición inválida sin traza, resultados vacíos, redirección de rutas protegidas y conversión de fallo de almacenamiento en 502 seguro. También se detuvo MinIO temporalmente: la API mantuvo salud HTTP 200 y PostgreSQL siguió aceptando conexiones; MinIO quedó restaurado. Pendientes integración de evidencia, CI y revisión. Informe: `evidencias de actividades/26-nov-2026/S4-SomnGuard-estabilidad/inicio-verificacion.md`. |
| S5 | Alcanzar cobertura de pruebas unitarias de al menos 70% por repositorio y CI verde. | Reportes de cobertura por repositorio y ejecuciones verdes. | No | Verificar reportes actuales y enlazarlos. |
| S6 | Evitar secretos expuestos en código o historial. | Revisión de archivos y del historial de repositorios, sin contraseñas ni claves expuestas. | No | Verificar al corte final; no registrar secretos en la bitácora. |
| S7 | Mantener el código en inglés. | Identificadores, comentarios, logs, rutas, tablas y mensajes de commit en inglés. | No | Verificar consistencia en los repositorios. |
| S8 | Mantener documentación con referencias APA 7 reales y declaración de uso de IA en cada documento y repositorio. | Referencias existentes y coincidentes con las citas; declaración de IA donde corresponda. | No | Verificar documento por documento. |
| S9 | Completar `08-somnguard` dentro del PR #15 con carpetas 01 a 09 y dos videos dentro de la duración solicitada. | PR con el paquete completo. | Sí (O) | Revalidar el contenido y estado actual del PR #15. |
| S10 | Crear la etiqueta `final-delivery-2026` en `main` de todos los repositorios y publicar dos ZIP por repositorio con SHA-256 coincidentes en un Release; un solo PR debe tocar únicamente la carpeta del proyecto. | Etiquetas, Release, dos ZIP por repo con hashes verificados y PR con alcance correcto. | Sí (O) | Pendiente de validación integral al cierre. |
| S11 | Sincronizar la documentación con el sistema construido. | Requisitos, diseño, pruebas, manuales y artículo consistentes con la versión entregada. | No | Revisar antes del corte final. |

## C. Compromisos individuales de Johan

| Ítem | Actividad del Acta | Evidencia requerida | Obligatorio | Estado verificado al corte |
|---|---|---|---|---|
| I1 | Firmar todos los commits desde el inicio del plan con identidad propia. | Historial de commits con firma GitHub `Verified` e identidad de Johan. | Sí (O) | Los commits consultados en web-shell y bitácora aparecen `Verified`; mantenerlo en cada commit nuevo. |
| I2 | Mantener bitácora diaria del 14 de noviembre al 4 de diciembre con actividad real cada día hábil. | Archivos diarios fechados, avances y enlaces a evidencia; registrar ausencia o bloqueo con veracidad. | Sí (O) | En curso. La entrada del 18 deja constancia de ausencia; la recuperación se registra en sus fechas reales, no retroactivamente. |
| I3 | Revisar PR de compañeros entre controles. | Al menos dos revisiones a PR de compañeros en cada intervalo de control, con comentarios comprobables. | No | Llevar conteo por intervalo. En PR #49 y #50 se solicitaron revisores, pero aún no se ha recibido ninguna revisión; esto no cuenta todavía como revisiones propias de Johan a PR de compañeros. |
| I4 | Aportar a SomnGuard al menos el 17,5% de commits netos y líneas propias de la participación del equipo. | Cálculo reproducible al corte, excluyendo andamiaje, merges y archivos generados. | No | Recalcular con la historia completa; el Acta citó 6% en su corte del 4 de noviembre. |
| I5 | No dejar defectos graves P0/P1 atribuibles al código propio. | Revisión del backlog y evidencia de corrección o ausencia de esos defectos. | No | Verificar con el equipo y al corte final. |
| I6 | Sustentar en vivo y realizar un cambio en vivo sobre código propio. | Demostración comprensible del código y cambio realizado por Johan. | Sí (O) | Pendiente de coordinación y evidencia en la sustentación. |

## D. Controles y fechas del plan

Las fechas de control aparecen como propuesta del instructor y deben confirmarse en la reunión:

| Fecha propuesta | Control / entrega | Preparación esperada |
|---|---|---|
| Viernes 20 de noviembre, 6:00 p. m. | Control 1 | Estado de bitácora, commits firmados y primeras revisiones. |
| Viernes 27 de noviembre, 6:00 p. m. | Control 2 | PR con CI verde y aprobaciones. |
| Viernes 4 de diciembre, 6:00 p. m. | Congelación/cierre del trabajo | Lo que llegue después no cuenta para el plan. |
| Sábado 5 de diciembre, hora por concertar | Entrega y sustentación | Sustentar ante los instructores los ítems y el código propio. |

**Resultado reportado de Control 1 (20/11):** Johan informa que los instructores no realizaron el control. No se atribuyen a esa fecha revisión ni acuerdos no presenciados; si se reprograma, se registrará en la fecha efectiva.

## E. Orden de trabajo para los registros diarios

Esta secuencia es una guía operativa, no una asignación diaria contenida en los PDF:

1. **Desbloquear validaciones externas:** confirmar con el instructor el procedimiento de revisores y usuarios de prueba; no enviar solicitudes ni crear cuentas sin autorización.
2. **Cerrar la línea de design-software:** publicar cambios con commits `Verified`, obtener revisiones válidas, confirmar CI y fusionar los PR aprobados a `develop`.
3. **Cerrar SomnGuard:** demostrar S1, conseguir cuentas autorizadas para S2 y probar los flujos reales requeridos por S3/S4.
4. **Completar la evidencia transversal:** cobertura, seguridad, idioma, citas/declaración de IA, paquete final, etiquetas, ZIP y hashes.
5. **Preparar la entrega:** reconciliar porcentaje de contribución, defectos, bitácora, revisiones y sustentación/cambio en vivo.

Cada entrada diaria debe registrar solo lo que efectivamente se hizo, la evidencia producida, resultados medidos y pendientes. Si un día hábil no hubo trabajo, dejar constancia veraz; no crear resultados retrospectivos.

## Fuentes y trazabilidad

- Acta 11-2026, de 13 de noviembre de 2026, adjunta al correo del instructor.
- Copia PDF del correo y del plan: `pdf-correo-plandemejoramiento.pdf` (carpeta `OneDrive/Pictures/Screenshots`).
- La copia de Acta separada indicada originalmente en Descargas no estaba disponible localmente al elaborar esta matriz; se contrastó con el Acta adjunta al correo.
- Estado técnico registrado en la bitácora hasta el 25 de noviembre de 2026 y PR #49; volver a validar estados que cambien en GitHub.
