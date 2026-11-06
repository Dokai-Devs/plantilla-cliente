# Plantilla de proyecto de cliente

Es la base de cada proyecto nuevo de un cliente de DokaiDevs. Un repo nuevo se crea con **Use this template**. Ese repo es privado y queda en la organización del cliente cuando la cuenta es suya.

Todavía está vacía. Se construye en las etapas 3 y 4 del plan de formación.

## Stack

- Next.js 16 (App Router) con TypeScript y Tailwind CSS.
- Supabase: Postgres, Auth y RLS, usado con `supabase-js` y la sesión del usuario.
- Zod para validar lo que entra.
- Vitest para los tests.
- Vercel, con un preview por PR y variables separadas por entorno.

## Reglas de la plantilla

- Los datos se leen y se escriben con `supabase-js` y la sesión del usuario. Nada de Prisma ni Drizzle: se conectan con un rol que saltea RLS.
- El esquema cambia solo con migraciones en `supabase/migrations`. Nunca a mano en producción.
- Toda tabla con datos de usuarios tiene RLS y un test que prueba que otro usuario no la ve.
- Los tipos de TypeScript se generan desde la base.
- Las claves van en Vercel o en el gestor de contraseñas. El repo solo tiene un `.env.example`.

## Qué tiene que tener

**Etapa 3**
- [ ] App de Next.js 16 desplegada en Vercel, con un preview por PR.
- [ ] Variables por entorno documentadas en `.env.example`.

**Etapa 4**
- [ ] Login y logout con Supabase Auth.
- [ ] Una tabla de ejemplo con RLS y su test.
- [ ] Migraciones en `supabase/migrations`.
- [ ] Un webhook de entrada que valida con Zod.
- [ ] CI con lint, typecheck y tests.
- [ ] Este README explica cómo levantarla en local y cómo crear un proyecto nuevo desde la plantilla.
