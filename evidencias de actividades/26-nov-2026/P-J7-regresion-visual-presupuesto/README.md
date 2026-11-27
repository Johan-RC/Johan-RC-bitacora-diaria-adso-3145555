# P-J7 — Regresión visual y presupuesto de compilación

**Fecha de trabajo:** 26 de noviembre de 2026  
**Repositorio:** `code-sena/design-software-web-shell`  
**Rama local:** `recovery/2026-11-26-pj7-visual-budget`

## Evidencia archivada

- `01-shell-home-chromium-linux.png`: captura real de `#main-content` tomada por Playwright al generar la referencia visual de Inicio en Chromium de `mcr.microsoft.com/playwright:v1.64.0-noble`. La prueba confirmó que la fuente Inter del sistema de diseño estaba cargada.

## Verificaciones locales

- `npm run build`: correcto.
- `node scripts/check-bundle-budget.mjs`: correcto; JavaScript 316.225/350.000 bytes y CSS 22.204/25.000 bytes.
- `npm run typecheck:e2e`: correcto.
- ESLint focalizado en la prueba, el script de presupuesto y `vite.config.ts`: correcto.
- Ejecución de la prueba visual durante la generación de la referencia: 1/1 correcta.

## Estado y límite

P-J7 sigue en curso. El commit firmado `b3ac09c` está publicado en `recovery/2026-11-26-pj7-visual-budget`; el [PR #51](https://github.com/code-sena/design-software-web-shell/pull/51) está abierto hacia `develop`, con revisiones solicitadas a `ariel5253`, `cjsarasty456` y `javierpintod`. El CI #76 está en ejecución. La imagen es una referencia y evidencia de ejecución local; no representa una corrida verde de GitHub Actions.
