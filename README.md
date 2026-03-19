# CórdobaProp — Asistente Inmobiliario IA 🏡

[![Demo](https://img.shields.io/badge/demo-cordobaprop.vercel.app-E8A838?style=flat-square)](https://cordobaprop.vercel.app)
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square)](CONTRIBUTING.md)

PWA gratuita que combina IA (Google Gemini) con datos del mercado inmobiliario de Córdoba, Argentina. Corre 100% en el browser del usuario — sin backend, sin costos de servidor.

![Screenshot](https://cordobaprop.vercel.app/icons/icon-512.png)

---

## ¿Qué hace?

- **Chat con IA** — consultas en lenguaje natural sobre propiedades, zonas y precios
- **Búsqueda con filtros** — por operación, tipo y dormitorios
- **Calculadora ROI** — rentabilidad neta con vacancia y gastos de entrada
- **Calculadora UVA** — cuota hipotecaria inicial
- **Análisis por zonas** — 5 zonas de Córdoba con stats de mercado
- **Modo Inversor** — 3 escenarios (conservador / equilibrado / agresivo)
- **PWA instalable** — funciona como app nativa en Android e iOS

## Stack

```
HTML + CSS + Vanilla JS   (sin frameworks, sin bundler)
Google Gemini API         (gemini-flash-latest, gratis hasta 1M tokens/día)
Vercel                    (deploy estático)
PWABuilder                (empaquetado Android)
```

## Correr en local

```bash
git clone https://github.com/eikujaime/cordobaprop.git
cd cordobaprop/cordobaprop

# Cualquier servidor estático sirve, por ejemplo:
npx serve .
# o
python3 -m http.server 3000
```

Abrí `http://localhost:3000`, ingresá tu clave de [Google AI Studio](https://aistudio.google.com/apikey) y listo.

## Estructura

```
cordobaprop/
└── cordobaprop/
    ├── index.html      ← toda la app (HTML + CSS + JS inline)
    ├── manifest.json   ← config PWA
    ├── sw.js           ← service worker
    └── icons/          ← íconos de la app
```

## Roadmap / Issues abiertos

Estas son las mejoras más pedidas. **Pull requests bienvenidos** — ver [CONTRIBUTING.md](CONTRIBUTING.md).

| # | Feature | Dificultad | Etiqueta |
|---|---------|-----------|---------|
| 1 | Integración con API de Zonaprop / Argenprop | Alta | `integración` |
| 2 | Soporte multi-ciudad (Rosario, Mendoza, CABA...) | Media | `multi-ciudad` |
| 3 | Calculadora de impuestos / ARBA / sellos | Baja | `calculadora` |
| 4 | Calculadora de expensas estimadas | Baja | `calculadora` |
| 5 | Calculadora de rentabilidad Airbnb | Media | `calculadora` |
| 6 | Comparador de zonas lado a lado | Media | `feature` |
| 7 | Historial de consultas guardado | Baja | `feature` |
| 8 | Modo oscuro / claro toggle | Baja | `diseño` |
| 9 | Soporte para OpenAI / Claude además de Gemini | Media | `integración` |

## Deploy

El proyecto se despliega automáticamente en Vercel al hacer push a `main`. Para hacer tu propio fork:

1. Fork este repo
2. Importá en [vercel.com](https://vercel.com) → **Root Directory**: `cordobaprop`
3. Deploy automático en cada push

## Licencia

MIT — hacé lo que quieras, pero si lo mejorás compartí los cambios 🙌
