# Revisiones pendientes y aprobaciones

**Actualizado:** 25 de noviembre de 2026. Este archivo organiza revisiones; no envía solicitudes.

## SomnGuard — PR #48 y PR #39

- [PR #48 — notificaciones push de eventos críticos](https://github.com/SomnGuard/somnguard-api/pull/48): fusionada el 6 de octubre de 2026.
- [PR #39 — consulta de eventos con filtros y paginación](https://github.com/SomnGuard/somnguard-api/pull/39): fusionada el 22 de septiembre de 2026.
- Ambas aparecen cerradas y fusionadas, sin comentarios de revisión en su historial; por tanto, no son solicitudes pendientes de aprobación.

## P-J5 — Modelo STRIDE de federación

- Repositorio: `code-sena/design-software-web-shell`.
- PR: [#49 — evidencia P-J4 y borrador P-J5](https://github.com/code-sena/design-software-web-shell/pull/49), rama `recovery/2026-11-23-pj4-pj5-evidence` hacia `develop`.
- Revisión técnica a solicitar cuando el instructor lo autorice: validar allowlist de remotes/orígenes, CSP y procedencia de artefactos, límites de carga/fallback y autorización en APIs.
- CI inicial: navegador aprobado; despliegue E5 omitido; ESLint falló por globals de Node/browser no declarados en el script P-J4. La configuración se corrigió localmente y lint pasa; falta publicar la corrección y repetir CI. El plan requiere dos aprobaciones de compañeros no coautores. No se han solicitado revisores, conforme al acuerdo de consultar primero al instructor.
## P-J4 — Métricas de web-shell

- Repositorio: `code-sena/design-software-web-shell`; evidencia incluida en el PR [#49](https://github.com/code-sena/design-software-web-shell/pull/49) hacia `develop`.
- Evidencia local: `evidence/pj4/P-J4-web-vitals-2026-11-23.md`, `results.json`, script y capturas. Mediana de laboratorio con mocks: LCP 248 ms, INP 24 ms y CLS 0.01172; no representa un MFE real ni tráfico de producción.
- La prueba del navegador pasó; el CI está parcialmente bloqueado por el ESLint del script, ya corregido localmente pero aún no publicado. Para el cierre faltan nuevo CI verde y dos aprobaciones de compañeros no coautores; las solicitudes quedan en espera de consultar al instructor.
