# Evidencia S1 — Arranque limpio de SomnGuard

**Grabación:** 25 de noviembre de 2026  
**Tipo:** ejecución local de desarrollo, aislada del entorno existente.  
**Video:** [SomnGuard-arranque-desde-cero-2026-11-25.mp4](SomnGuard-arranque-desde-cero-2026-11-25.mp4)

## Qué muestra

1. Inicio de PostgreSQL 16 con somnguard-db/.env.example en un proyecto Docker nuevo; el contenedor llega a healthy.
2. Ejecución de Liquibase con el procedimiento del repositorio: **92 changesets aplicados**, 92 filtrados por contexto, 184 en total.
3. Arranque de MailHog y S3Mock para el entorno local.
4. Inicio de la API con Spring Boot y verificación GET /actuator/health → UP.
5. Inicio del portal con VITE_API_URL de somnguard-portal/.env.example; responde HTTP 200 y se muestra la página en Edge.

## Capturas

- [PostgreSQL saludable](01-postgres-healthy.jpg)
- [Migraciones Liquibase](02-liquibase-aplicado.jpg)
- [API saludable](03-api-health-up.jpg)
- [Portal HTTP 200](04-portal-http-200.jpg)
- [Portal abierto en navegador](05-portal-vista-local.jpg)

## Nota sobre la guía

La guía SomnGuard/somnguard-docs/docs/10-devops/local-setup.md menciona el perfil develop y la ruta /health. En este checkout está application-dev.yml y Actuator publica la salud en /actuator/health; la demostración usó dev y esa ruta real. La configuración se tomó de .env.example; no se mostró ni modificó ningún .env local.

## Alcance

La prueba usa servicios locales y una base nueva. No se usaron datos productivos, no se crearon cuentas ni se probó autenticación. Al terminar se detuvieron los contenedores sin borrar el volumen; quedó conservada la base de esta ejecución. Para repetir desde una base vacía, hay que usar otro nombre de proyecto Docker o limpiar únicamente el volumen aislado de esta evidencia.

Este video aporta evidencia del arranque local. No confirma que reemplace la demostración ante el Instructor; eso requiere aceptación de los instructores.
