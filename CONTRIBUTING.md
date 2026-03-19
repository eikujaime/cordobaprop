# Cómo contribuir a CórdobaProp

¡Gracias por tu interés! Este proyecto es simple a propósito: una sola PWA en HTML/JS, sin build tools, fácil de modificar.

## Antes de empezar

- Revisá los [issues abiertos](https://github.com/eikujaime/cordobaprop/issues) — quizás ya hay alguien trabajando en lo mismo
- Para cambios grandes, abrí un issue primero para discutir el enfoque
- Para bugs o mejoras pequeñas, el PR directo está perfecto

## Setup local

```bash
git clone https://github.com/eikujaime/cordobaprop.git
cd cordobaprop/cordobaprop
npx serve .
```

Necesitás una clave gratuita de [Google AI Studio](https://aistudio.google.com/apikey) para probar el chat.

## Flujo de trabajo

```bash
# 1. Creá tu rama
git checkout -b feature/nombre-descriptivo

# 2. Hacé los cambios en cordobaprop/index.html
# (o agregá archivos nuevos si la feature lo requiere)

# 3. Probá en el browser antes de commitear

# 4. Commit con mensaje claro
git commit -m "feat: agrega calculadora de expensas"

# 5. Push y abrí el PR
git push origin feature/nombre-descriptivo
```

## Convenciones de commits

```
feat:     nueva funcionalidad
fix:      corrección de bug
docs:     cambios en documentación
style:    cambios de CSS/diseño sin afectar lógica
refactor: reorganización de código
```

## Áreas prioritarias

### 🔌 Integración con portales (Alta prioridad)
Lo más pedido. Opciones posibles:
- **Proxy CORS** — un worker de Cloudflare que intermedie llamadas a Zonaprop/Argenprop
- **API oficial** — Argenprop tiene API privada; Zonaprop no tiene pública documentada
- **Scraping del lado cliente** — limitado por CORS, requiere extensión o proxy
- **Feed RSS / JSON** — algunos portales exponen feeds parciales

### 🌆 Multi-ciudad (Media prioridad)
El `SYSTEM` prompt en `index.html` tiene los datos de Córdoba hardcodeados. La idea sería:
- Agregar un selector de ciudad en el setup o header
- Cargar el prompt de cada ciudad desde un objeto/archivo separado
- Empezar con Rosario y Mendoza (mercados similares con datos disponibles)

### 🧮 Más calculadoras (Baja prioridad / buen punto de entrada)
Calculadoras que faltan y serían útiles:
- **Sellos / ARBA** — impuesto de sellos varía por provincia (Córdoba: 1.5% del valor escriturado)
- **Expensas estimadas** — en función de m² y zona
- **Rentabilidad Airbnb** — ocupación estimada × precio/noche × temporada
- **Comparador** — dos propiedades lado a lado con métricas

## Estructura del código

Todo está en `index.html`. Las secciones principales:

| Línea aprox. | Contenido |
|---|---|
| 1–20 | `<head>` — meta tags, fuentes |
| 21–200 | `<style>` — todo el CSS con variables CSS |
| 201–350 | HTML estático — pantallas, nav, páginas |
| 351–501 | `<script>` — lógica JS, SYSTEM prompt, llamadas a Gemini |

El **SYSTEM prompt** está en la constante `SYSTEM` dentro del `<script>`. Es el lugar más fácil para mejorar el comportamiento del asistente.

## ¿No sabés por dónde empezar?

Buscá issues con la etiqueta `good first issue`. Algunas ideas fáciles:
- Agregar una zona nueva al análisis de zonas
- Mejorar el texto del SYSTEM prompt para una consulta específica
- Agregar un chip de acceso rápido en el chat
- Mejorar el diseño de alguna tarjeta

## Preguntas

Abrí un issue con la etiqueta `question` o escribí en las Discussions del repo.
