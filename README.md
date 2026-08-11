# emweb-site — Sitio comercial de EMG

Sitio público de marketing de EMG, servido en **www.emweb.online**.

> Especificación completa (qué construir): ver el documento **Brief: Sitio Comercial**
> en la documentación interna (`Base/docs/brief_sitio_comercial.md` o
> `/admin/docs/brief-sitio-comercial`).

## Qué es esto

- Sitio **estático** (marketing). NO es la app ni el portal de clientes.
- Hosting: **Cloudflare Pages** (gratis).
- Dominio: `www.emweb.online` (+ apex `emweb.online`).
- NO tocar los subdominios `gestion.` (app) ni `app.` (Cucchetti/updates).

## Stack

- Recomendado: **Astro + Tailwind CSS** (a definir con el equipo).
- Alternativa simple: **HTML + Tailwind** puro.
- El colaborador puede reemplazar el `index.html` placeholder por el proyecto real.

## Estado actual

- `index.html`: página provisional "en construcción" (desplegable ya).

## Cómo desplegar en Cloudflare Pages

1. El **dueño de la cuenta** crea el proyecto en Cloudflare → Workers & Pages → Pages.
2. Conecta este repositorio (deploy automático en cada push) o usa subida directa.
3. Si es Astro: build command `npm run build`, output `dist`.
   Si es HTML puro: sin build, output = raíz del repo.
4. Asignar el dominio `www.emweb.online` (y redirigir el apex).

## Flujo de trabajo

- Trabajar en ramas + Pull Request.
- Cloudflare Pages genera **preview** por rama; revisar antes de publicar a producción.
- Entregar por etapas: estructura + textos → diseño → formulario de contacto.
