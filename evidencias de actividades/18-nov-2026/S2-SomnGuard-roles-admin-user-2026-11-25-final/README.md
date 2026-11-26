# SomnGuard - prueba local de roles admin y user
**Fecha:** 25 de noviembre de 2026  
**Tipo:** base PostgreSQL temporal aislada, creada desde .env.example.

## Resultado
- Se registraron dos cuentas sinteticas con POST /api/v1/auth/register.
- Los correos se verificaron mediante MailHog local; no se uso Gmail ni se enviaron correos externos.
- La cuenta user inicio sesion y su JWT incluyo el rol user.
- La cuenta admin inicio sesion y su JWT incluyo el rol admin.
- En GET /api/v1/users, admin recibio HTTP 200 y user HTTP 403.
- No se guardaron contrasenas, codigos de verificacion, tokens ni cuentas en archivos.

## Limite de aprovisionamiento
El repositorio no proporciona una cuenta administrativa inicial en la base limpia. Para esta prueba, el rol admin se asigno unicamente en la base descartable local luego del registro; esta maniobra no se aplico a ninguna instancia externa ni debe usarse como procedimiento de produccion.

## Limpieza
Al final se detienen la API y los contenedores. El volumen aislado se conserva; puede contener cuentas sinteticas de pruebas previas y de esta corrida, sin usuarios reales ni contrasenas persistidas.
