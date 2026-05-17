# PaperBOT Dashboard — Guía de Despliegue en GitHub Pages

Este directorio contiene la aplicación web estática (SPA) de gestión visual de revisiones y tareas operativas para el proyecto `Deivs117/PaperBOTCorrection`.

---

## 📋 Descripción General

El dashboard es una aplicación de una sola página (SPA) que opera completamente en el navegador sin necesidad de un servidor backend. Utiliza un sistema de persistencia jerárquico:

1. **`frontend/data.json`** — Estado maestro del equipo (fuente de verdad).
2. **`localStorage`** del navegador — Estado personal del usuario.
3. **Datos por defecto** — Precargados desde `REVIEWERS_PETITIONS.md`.

Para actualizar el estado maestro del equipo: usa el botón **"Exportar Estado Actual (JSON)"** y sube el archivo `data.json` descargado a la carpeta `frontend/` del repositorio.

---

## 🚀 Opción 1 — Despliegue Manual vía GitHub Pages (Interfaz Web)

### Paso 1: Accede a la configuración del repositorio

1. Ve a `https://github.com/Deivs117/PaperBOTCorrection`
2. Haz clic en la pestaña **Settings** (ícono de engranaje en la barra superior)
3. En el menú lateral izquierdo, busca la sección **Pages**

### Paso 2: Configura la fuente de despliegue

En la sección **"Build and deployment"**:

1. En **Source**, selecciona **"Deploy from a branch"**
2. En **Branch**, selecciona `main`
3. En el selector de carpeta, selecciona **`/docs`** o configura el workflow de GitHub Actions (Opción 2 recomendada)

> ⚠️ **Nota importante:** GitHub Pages sólo admite despliegue desde la raíz (`/`) o desde la carpeta `/docs` de una rama. Como los archivos están en `/frontend`, se recomienda usar la **Opción 2 (GitHub Actions)** para publicar directamente desde ese subdirectorio sin mover archivos.

### Paso 3: Guarda la configuración

Haz clic en **Save**. GitHub Pages tardará unos minutos en generar el sitio. Una vez activo, podrás acceder en:

```
https://deivs117.github.io/PaperBOTCorrection/
```

---

## ⚡ Opción 2 — Despliegue Automatizado vía GitHub Actions (Recomendado)

Este método publica automáticamente el contenido de la carpeta `/frontend` en la rama `gh-pages` cada vez que se hace un `git push` a `main`.

### Paso 1: Crea el archivo de workflow

Crea el archivo `.github/workflows/deploy-frontend.yml` en el repositorio con el siguiente contenido exacto:

```yaml
name: Deploy Frontend to GitHub Pages

on:
  push:
    branches:
      - main
    paths:
      - 'frontend/**'
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  deploy:
    name: Deploy to GitHub Pages
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Setup Pages
        uses: actions/configure-pages@v5

      - name: Upload Frontend Folder as Artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./frontend

      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

### Paso 2: Habilita GitHub Pages con GitHub Actions

1. Ve a **Settings → Pages**
2. En **Source**, selecciona **"GitHub Actions"**
3. Guarda la configuración

### Paso 3: Realiza un push para activar el workflow

```bash
git add .github/workflows/deploy-frontend.yml
git commit -m "chore: add GitHub Pages deployment workflow"
git push origin main
```

El workflow se ejecutará automáticamente. Monitoréalo en la pestaña **Actions** del repositorio.

Una vez completado, el dashboard estará disponible en:

```
https://deivs117.github.io/PaperBOTCorrection/
```

---

## 🔄 Flujo de Trabajo del Equipo

### Para sincronizar el estado entre autores:

```
┌─────────────────────────────────────────────────────────┐
│  Autor A realiza cambios en el dashboard                │
│  → Clic en "Exportar Estado Actual (JSON)"              │
│  → Se descarga data.json                                │
│  → Sube data.json a frontend/ en GitHub                 │
│  → GitHub Actions redesplega automáticamente            │
│  → Autor B recarga la página y obtiene el nuevo estado  │
└─────────────────────────────────────────────────────────┘
```

### Estructura de archivos del frontend:

```
frontend/
├── index.html        ← SPA principal (este archivo)
├── data.json         ← Estado maestro del equipo (actualizar para sincronizar)
└── README.md         ← Esta guía
```

---

## 🛠️ Desarrollo Local

Para probar el dashboard localmente, necesitas un servidor HTTP simple (los navegadores bloquean `fetch()` con el protocolo `file://`):

```bash
# Con Python 3
cd frontend
python -m http.server 8080

# Con Node.js (npx)
npx serve frontend

# Con VS Code: instala la extensión "Live Server"
```

Luego abre `http://localhost:8080` en tu navegador.

---

## 📦 Dependencias CDN

El dashboard carga las siguientes librerías desde CDN (sin instalación local):

| Librería | Versión | CDN |
|---|---|---|
| Tailwind CSS | v3 (Play CDN) | `cdn.tailwindcss.com` |
| Chart.js | v4.4.0 | `cdn.jsdelivr.net` |

No se requiere `npm install` ni build step.

---

## 👥 Roster del Equipo

| Apodo | Nombre |
|---|---|
| `SapoMarapo` | Sebas |
| `Flagugu` | Sam |
| `Homo` | Deiv |
| `Negriche` | Dieguito |
