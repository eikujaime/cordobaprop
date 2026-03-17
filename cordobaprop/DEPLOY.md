# 🚀 Guía de Deploy — CórdobaProp PWA

## PASO 1 — Subir a GitHub (2 min)

1. Entrá a **github.com** → New repository
2. Nombre: `cordobaprop`
3. Marcá "Public" → Create repository
4. Subí todos los archivos:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - carpeta `icons/` con todas las imágenes

---

## PASO 2 — Deploy en Vercel (1 min, gratis)

1. Entrá a **vercel.com** e iniciá sesión con GitHub
2. Clic en "Add New Project"
3. Seleccioná tu repo `cordobaprop`
4. Clic en **Deploy** (sin configurar nada)
5. Tu app queda en: `https://cordobaprop.vercel.app`

---

## PASO 3 — Google Play Store (via PWABuilder)

1. Entrá a **pwabuilder.com**
2. Pegá la URL de tu app: `https://cordobaprop.vercel.app`
3. Clic en "Package for stores" → Android
4. Descargás el archivo `.aab` (Android App Bundle)
5. Subís el `.aab` a **play.google.com/console**
   - Costo único: USD 25 para registrarte como desarrollador
   - Tiempo de revisión: 3-7 días

---

## PASO 4 — App Store iOS (via PWABuilder)

1. En **pwabuilder.com**, elegí "iOS" en "Package for stores"
2. Descargás el paquete `.zip` con el proyecto Xcode
3. Necesitás:
   - Una Mac con Xcode instalado (o usar MacInCloud ~USD 1/hora)
   - Apple Developer Account: USD 99/año
4. Abrís el proyecto en Xcode → Archive → Submit to App Store
5. Tiempo de revisión: 1-3 días

---

## ALTERNATIVA RÁPIDA PARA IOS — Sin App Store

En iPhone los usuarios pueden instalar la PWA directo desde Safari:
1. Abrir `https://cordobaprop.vercel.app` en Safari
2. Tocar el botón compartir ↑
3. "Agregar a pantalla de inicio"
4. La app aparece como ícono nativo sin necesidad de App Store

---

## DOMINIO PERSONALIZADO (opcional, gratis con Vercel)

1. En Vercel → Settings → Domains
2. Agregás: `cordobaprop.com.ar`
3. Apuntás el DNS a Vercel (te da las instrucciones)
4. HTTPS automático incluido

---

## ESTRUCTURA DE ARCHIVOS

```
cordobaprop/
├── index.html       ← App completa
├── manifest.json    ← Configuración PWA
├── sw.js            ← Service Worker (offline)
└── icons/
    ├── icon-72.png
    ├── icon-96.png
    ├── icon-128.png
    ├── icon-144.png
    ├── icon-152.png
    ├── icon-192.png
    ├── icon-384.png
    ├── icon-512.png
    └── screenshot-mobile.png
```

---

## CHECKLIST PWA ✅

- [x] manifest.json con todos los íconos
- [x] Service Worker con cache offline
- [x] HTTPS (automático con Vercel)
- [x] Responsive / mobile-first
- [x] Meta tags Apple (iOS)
- [x] Banner de instalación (Android)
- [x] Safe area (iPhone con notch)
- [x] Shortcuts de app (accesos directos)
- [x] Push notifications (preparado)

---

*CórdobaProp PWA — Listo para Google Play y App Store*
