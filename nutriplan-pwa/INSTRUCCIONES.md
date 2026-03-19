# NutriPlan PWA — Instrucciones de instalación

## Archivos incluidos
- `index.html` — La aplicación completa
- `manifest.json` — Manifiesto PWA (nombre, icono, colores)
- `sw.js` — Service Worker (funciona offline)
- `icon-192.png` / `icon-512.png` — Iconos de la app

---

## Opción 1 — Desde un servidor web (recomendada)

Para que la PWA funcione correctamente necesita servirse por HTTPS.
Las opciones más sencillas y gratuitas:

### GitHub Pages (gratis, permanente)
1. Crea una cuenta en https://github.com
2. Nuevo repositorio → sube los 5 archivos
3. Ve a Settings → Pages → Source: main branch
4. Tu app estará en: `https://TU_USUARIO.github.io/NOMBRE_REPO/`

### Netlify Drop (gratis, instantáneo)
1. Ve a https://app.netlify.com/drop
2. Arrastra la carpeta `nutriplan-pwa` completa
3. En segundos tienes una URL pública con HTTPS

### Vercel (gratis)
1. Ve a https://vercel.com
2. Arrastra la carpeta o conecta con GitHub

---

## Instalar en Android (Chrome)

1. Abre la URL de tu app en **Chrome para Android**
2. Espera unos segundos — aparece un banner en la parte inferior:
   **"Añadir NutriPlan a la pantalla de inicio"**
3. Pulsa **Instalar**
4. La app aparece en tu pantalla de inicio con su propio icono

Si no aparece el banner automáticamente:
- Pulsa el menú ⋮ (tres puntos) de Chrome
- Selecciona **"Añadir a pantalla de inicio"** o **"Instalar app"**

---

## Instalar en iPhone / iPad (Safari)

1. Abre la URL en **Safari**
2. Pulsa el botón de compartir (cuadrado con flecha ↑)
3. Selecciona **"Añadir a pantalla de inicio"**
4. Confirma el nombre y pulsa **Añadir**

---

## Opción 2 — En tu red local (sin internet)

Si solo quieres usarla en tu casa sin subirla a internet:

1. Instala Python (ya lo tienes si usas Mac/Linux)
2. En la carpeta `nutriplan-pwa` ejecuta:
   ```bash
   python3 -m http.server 8080
   ```
3. Desde tu móvil (en la misma WiFi) abre:
   `http://TU_IP_LOCAL:8080`
   (Tu IP local suele ser algo como `192.168.1.XX`)

**Nota:** En red local sin HTTPS el Service Worker no se registra,
pero la app funciona igualmente. Solo no se instalará como PWA.

---

## ¿Cómo funciona offline?

Una vez instalada y abierta por primera vez con internet,
la app guarda todos sus archivos en caché. A partir de ahí
funciona completamente sin conexión. Tus datos se guardan
en el almacenamiento local del dispositivo (localStorage).
