# Evidencias de recuperación — bloque del 18 de noviembre

**Aprendiz:** Johan Steven Rodriguez Charry
**Cierre operativo del trabajo propio:** 26 de noviembre de 2026
**Fechas reales de ejecución:** 23 y 25 de noviembre de 2026; el cierre de registro se hizo el 26.

El 18/11 se conserva como ausencia laboral declarada. Las evidencias de recuperación no se atribuyen retroactivamente a esa fecha.

## P-J4 y P-J5 — web-shell

- [PR #49 — evidencia P-J4 y borrador P-J5](https://github.com/code-sena/design-software-web-shell/pull/49), hacia develop.
- [CI #72](https://github.com/code-sena/design-software-web-shell/actions/runs/45710346454): checks estáticos, pruebas unitarias, build y navegador en verde; el manifiesto contra entorno desplegado quedó omitido.
- P-J4: tres corridas, mediana LCP 248 ms, INP 24 ms, CLS 0.01172. El remote es simulado y las cifras son de laboratorio.
- P-J5: borrador STRIDE documentado; su revisión técnica aún está pendiente.
- Las capturas 01–06 registran CI, mediciones, documento, archivos del PR y commits verificados.

**En espera externa:** por instrucción, el PR #49 no se consultó ni modificó en este cierre. Su último estado registrado era pendiente de revisiones/aprobaciones e integración en develop; no se intentó fusionar. El Acta exige que los cambios queden en develop con CI y dos aprobaciones, así que esta evidencia no se presenta como aprobación formal.

## S1 — arranque limpio de SomnGuard

- [Video y capturas del arranque local](S1-SomnGuard-arranque-desde-cero-2026-11-25-final/README.md): PostgreSQL healthy, 92 changesets de Liquibase, API saludable y portal HTTP 200, partiendo de una base local nueva con manual y .env.example, sin modificar código.
- El Acta menciona sustentación en vivo ante instructores. El video demuestra el procedimiento local; no se afirma que los instructores hayan aceptado sustituir la demostración en vivo.

## S2 — roles admin y user

- [Video, capturas e informe de la prueba local](S2-SomnGuard-roles-admin-user-2026-11-25-final/README.md): cuentas sintéticas en base local aislada; admin obtuvo HTTP 200 y user HTTP 403 en GET /api/v1/users.
- No se publicaron contraseñas, códigos ni tokens. El rol admin se asignó solo en la base temporal de prueba; no es una cuenta administrativa de producción.

## Resultado del cierre

Quedó cerrada la recuperación y publicación del trabajo que estaba bajo control de Johan. Permanecen anotadas las dependencias de revisión del PR y de evaluación de la evidencia S1; no se marcan como aprobadas por el instructor.
