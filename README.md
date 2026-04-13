# Notilea — Portal de Noticias

> Lo que pasa en tu barrio y lo que sacude al país y al planeta

## 🚀 Publicar en GitHub Pages (3 pasos)

### 1. Subir a GitHub
```bash
# Crear repositorio en github.com/new  con nombre: notilea
git init
git add .
git commit -m "🗞️ Notilea v1.0"
git remote add origin https://github.com/TU_USUARIO/notilea.git
git push -u origin main
```

### 2. Activar GitHub Pages
- Ve a tu repo → **Settings** → **Pages**
- Source: **Deploy from a branch**
- Branch: `main` / `/ (root)`
- Clic en **Save**

Tu sitio estará en: `https://TU_USUARIO.github.io/notilea/`

### 3. Actualizar la URL base
En `js/app.js`, línea 7:
```js
const SITE_URL = 'https://TU_USUARIO.github.io/notilea';
```

En `index.html`, actualizar las meta OG:
```html
<meta property="og:url" content="https://TU_USUARIO.github.io/notilea/">
<meta property="og:image" content="https://TU_USUARIO.github.io/notilea/images/og-cover.png">
<meta name="twitter:image" content="https://TU_USUARIO.github.io/notilea/images/og-cover.png">
```

---

## 📁 Estructura de archivos

```
notilea/
├── index.html          ← Portada principal
├── css/
│   └── style.css       ← Todos los estilos
├── js/
│   └── app.js          ← Datos de noticias + lógica
├── images/
│   └── og-cover.png    ← Imagen OG (1200×630) para previews
└── README.md
```

## ✍️ Cómo agregar noticias

En `js/app.js`, agrega un objeto al array `NEWS`:

```js
{
  id: 'mi-noticia',           // ID único (sin espacios)
  cat: 'Paraguay · Política', // Categoría mostrada
  catClass: 'red',            // red | gold | blue | green | live
  title: 'Título de la noticia',
  byline: 'Autor · Fecha',
  summary: 'Resumen corto (aparece en la tarjeta)',
  img: 'images/mi-foto.jpg',  // o null si no hay foto
  date: '13 ABR 2026',
  source: 'ABC Color',
  ogDesc: 'Descripción para redes sociales',
  body: `
    <p>Primer párrafo...</p>
    <h3>Subtítulo</h3>
    <p>Más texto...</p>
  `
}
```

## 📱 Previews en redes sociales

| Red | Requisito | Estado |
|-----|-----------|--------|
| WhatsApp | og:image, og:title, og:description | ✅ |
| Facebook | og:image 1200×630, og:type | ✅ |
| Telegram | og:image, twitter:card | ✅ |
| Twitter/X | twitter:card = summary_large_image | ✅ |
| Discord | og:image, og:description | ✅ |
| LinkedIn | og:image, og:title | ✅ |

> **Tip:** Verificar previews en: https://developers.facebook.com/tools/debug/
> y https://cards-dev.twitter.com/validator

## 🛠️ Personalización rápida

| Qué cambiar | Dónde |
|-------------|-------|
| Colores | `css/style.css` → `:root` variables |
| Nombre del sitio | `index.html` → `<title>` y `.logo` |
| URL del sitio | `index.html` meta OG + `js/app.js` SITE_URL |
| Imagen OG | Reemplazar `images/og-cover.png` (1200×630 px) |
| Ticker de noticias | `index.html` → `.ticker-track` spans |
| Noticias | `js/app.js` → array `NEWS` |
