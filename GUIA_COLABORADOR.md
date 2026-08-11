# Guía del colaborador — Sitio comercial EMG

> Documento para el colaborador que va a construir y mantener el sitio comercial
> en `www.emweb.online`. Explica qué instalar, cómo trabajar y cómo entregar.

---

## 1. Qué es este proyecto

Un sitio **estático de marketing** (HTML/CSS, o Astro+Tailwind). NO es la app web
del ERP ni un sistema con base de datos. Es la cara pública de EMG para que
posibles clientes conozcan el producto y soliciten una demo.

El sitio se sirve desde Cloudflare Pages. El deploy a producción lo hace
el dueño del proyecto (no el colaborador).

---

## 2. Qué instalar en tu PC

1. **Git** — [git-scm.com/downloads](https://git-scm.com/downloads)
2. **Node.js (LTS)** — [nodejs.org](https://nodejs.org)
3. **Visual Studio Code** — [code.visualstudio.com](https://code.visualstudio.com)

Extensiones recomendadas para VS Code:
- Astro (si se usa Astro)
- Tailwind CSS IntelliSense
- Live Server (para preview local rápida con HTML puro)
- GitLens (opcional, para ver historial de Git)

---

## 3. Clonar el repositorio (una sola vez)

```bash
git clone https://github.com/eliasmerlino91-commits/emweb-site.git
cd emweb-site
```

Abrí la carpeta en VS Code:
```bash
code .
```

---

## 4. Estructura del proyecto

```
emweb-site/
├── public/            ← archivos estáticos que se publican
│   └── index.html     ← página principal (reemplazá el placeholder por el sitio real)
├── wrangler.toml      ← configuración de Cloudflare (NO tocar salvo indicación)
├── .gitignore
├── README.md
└── GUIA_COLABORADOR.md  ← este documento
```

Todo lo que va a ser servido al público vive en **`public/`**. Imágenes, CSS,
JavaScript, fuentes → todo adentro de `public/`.

---

## 5. Probar localmente (preview en tu PC)

### Si es HTML puro:
Con la extensión **Live Server** de VS Code: clic derecho en `public/index.html`
→ "Open with Live Server". Se abre en el navegador y se recarga solo al guardar.

O desde terminal:
```bash
npx serve public
```
(Se abre en http://localhost:3000)

### Si se usa Astro (a definir):
```bash
npm install      # solo la primera vez
npm run dev      # servidor de desarrollo con recarga en vivo
```

---

## 6. Flujo de trabajo (cómo entregar cambios)

1. **Antes de empezar a trabajar**, actualizá tu copia local:
   ```bash
   git pull origin main
   ```

2. **Hacé tus cambios** en los archivos de `public/`.

3. **Commiteá** los cambios:
   ```bash
   git add .
   git commit -m "Descripción breve de lo que cambié"
   ```

4. **Pusheá** a GitHub:
   ```bash
   git push origin main
   ```

5. **Avisá al responsable** que hay cambios listos para revisar y desplegar.

> El deploy a producción (`www.emweb.online`) lo hace el responsable del proyecto
> con `wrangler deploy`. NO se publica automáticamente al pushear.

---

## 7. Reglas importantes

- **NO** tocar `wrangler.toml` salvo indicación explícita.
- **NO** borrar ni mover la carpeta `public/`.
- **NO** commitear secretos, contraseñas ni API keys al repo.
- **NO** tocar subdominios que no sean `www` (existen `gestion.` y `app.` para otros sistemas).
- Los archivos grandes (videos, PDFs pesados) se hablan antes de agregarlos.
- Respetar la identidad visual de EMG (logo, colores del design system).

---

## 8. Especificación de qué construir

Ver el documento **"Brief: Sitio Comercial"** en la documentación interna.
El responsable te lo va a compartir.

Resumen:
- Secciones: Hero, qué es EMG, verticales, módulos, beneficios, caso real, planes, contacto.
- Formulario de contacto que envíe por email.
- Responsive (celular + desktop).
- SEO básico (títulos, meta, sitemap).
- Performance objetivo: Lighthouse 90+.

---

## 9. Herramienta de deploy (solo para el responsable)

El responsable del proyecto despliega con:
```powershell
cd C:\Users\info\source\repos\emweb-site
git pull origin main
wrangler deploy
```

Eso sube los cambios a `www.emweb.online` en segundos.
