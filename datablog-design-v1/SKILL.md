---
name: datablog-design-v1
description: Aplica el sistema de diseño de angelgarciadatablog.com a un nuevo proyecto. Úsalo cuando el usuario quiera replicar el estilo de su web personal (dark mode, gradiente azul-morado-rosa, cards interactivas con hover, skeleton loading, responsive mobile-first).
---

# Sistema de Diseño — angelgarciadatablog v1

Cuando se invoque este skill, analiza el proyecto actual y aplica el sistema de diseño descrito aquí. Si el proyecto no tiene CSS, créalo. Si ya tiene estilos, adáptalos respetando los patrones definidos.

---

## 1. Identidad Visual

**Estética:** Dark mode minimalista. Inspirado en herramientas de datos (Linear, Analytics Vidhya).
**Personalidad:** Técnico pero accesible. Serio pero con vida (gradiente, animaciones sutiles).
**Color de firma:** Gradiente azul → morado → rosa.

---

## 2. Variables CSS (Design Tokens)

Siempre declarar estas variables en `:root`. Son la base de todo el sistema.

```css
:root {
  /* Fondos — 3 capas de profundidad */
  --bg: #0a0a0a;          /* Fondo base de la página */
  --surface: #141414;     /* Secciones alternadas, footer */
  --card-bg: #1a1a1a;     /* Tarjetas, formularios, inputs */

  /* Texto */
  --text: #ffffff;
  --text-secondary: #b0b0b0;

  /* Bordes */
  --border: #2a2a2a;
  --border-light: #1f1f1f;

  /* Estados */
  --success: #85d992;
  --danger: #f04438;

  /* Gradiente de firma: azul → morado → rosa */
  --gradient: linear-gradient(90deg, #2674ed 0%, #7c3aed 50%, #ec4899 100%);
  --gradient-hover: linear-gradient(90deg, #1e5dd8 0%, #6d28d9 50%, #db2777 100%);

  /* Colores sólidos de acento (para bordes y detalles) */
  --accent: #2674ed;
  --accent-mid: #7c3aed;
  --accent-end: #ec4899;

  /* Sombras */
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.5);
  --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.6), 0 2px 4px -1px rgba(0,0,0,0.4);
  --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.7), 0 4px 6px -2px rgba(0,0,0,0.5);
  --shadow-accent: 0 10px 25px -5px rgba(124,58,237,0.4), 0 4px 6px -2px rgba(124,58,237,0.3);
  --shadow-glow: 0 0 20px rgba(124,58,237,0.3);

  /* Radios */
  --radius: 12px;
  --radius-lg: 16px;
}
```

---

## 3. Base y Reset

```css
* { box-sizing: border-box; margin: 0; padding: 0; }

html {
  -webkit-font-smoothing: antialiased;
  overflow-x: hidden;
}

body {
  background: var(--bg);
  color: var(--text);
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  line-height: 1.6;
  overflow-x: hidden;
}
```

---

## 4. Layout — Contenedor

```css
.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 16px;
}

@media (min-width: 640px)  { .container { padding: 0 20px; } }
@media (min-width: 1024px) { .container { padding: 0 24px; } }
```

**Breakpoints del sistema:**
- `640px` — Tablet pequeña
- `768px` — Tablet
- `1024px` — Desktop
- `1200px` — Desktop ancho

---

## 5. Secciones

Las secciones alternan fondo `--bg` y `--surface` para crear ritmo visual sin líneas divisorias:

```css
.seccion-oscura { background: var(--bg);      padding: 80px 0; }
.seccion-media  { background: var(--surface); padding: 80px 0; }
```

---

## 6. Tipografía

| Uso | Tamaño | Peso | Notas |
|-----|--------|------|-------|
| Hero title | 36px → 64px (responsive) | 700 | `letter-spacing: -0.02em` |
| H2 de sección | 28px → 32px | 700 | `letter-spacing: 0.5px` |
| Cuerpo | 16px | 400 | `line-height: 1.6` |
| Secundario | 14-15px | 400 | `color: var(--text-secondary)` |
| Labels/meta | 13px | 400-500 | — |

**Texto con gradiente** (para títulos destacados):
```css
.gradient-text {
  background: var(--gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

---

## 7. Cards

Patrón base para cualquier tarjeta:

```css
.card {
  background: var(--card-bg);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 24px;
}
```

**Hover effect — solo en cards interactivas:**

El efecto hover (elevación + borde morado) **únicamente debe aplicarse cuando el card es un elemento clicable** — es decir, cuando envuelve un `<a>`, es un `<button>`, o tiene un `onclick` explícito. Aplicarlo en cards decorativas o de contenido crea confusión sobre qué elementos son interactuables.

```css
/* Solo cuando el card en sí es interactivo */
a.card:hover,
button.card:hover,
.card--interactive:hover {
  transform: translateY(-4px);
  border-color: rgba(124, 58, 237, 0.5);
  box-shadow: var(--shadow-accent);
  transition: all 0.3s ease;
}
```

> **Regla práctica:** Si al pasar el cursor no ocurre ninguna acción, el card no debe tener hover visual. El hover es una señal de interactividad, no decoración.

---

## 8. Botones — 3 variantes

**Cuándo usar cada uno:**
- `btn-primary` — solo para la acción más importante de toda la página (máximo 1 por vista). Nunca en cards ni slides internos.
- `btn-outline` — CTAs dentro de cards, dashboards, secciones internas. Es el botón por defecto en la mayoría de contextos.
- `btn-ghost` — acciones secundarias o de menor jerarquía.

**Primario** (relleno con gradiente — usar con criterio, máximo 1 por vista):
```css
.btn-primary {
  display: inline-block;
  background: var(--gradient);
  color: #fff;
  padding: 14px 32px;
  border-radius: 8px;
  border: none;
  font-weight: 600;
  font-size: 15px;
  text-decoration: none;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: var(--shadow-accent);
}
.btn-primary:hover {
  background: var(--gradient-hover);
  transform: translateY(-2px);
  box-shadow: var(--shadow-accent), var(--shadow-glow);
}
```

**Outline** (borde degradado, fondo transparente — es el botón estándar para CTAs en cards y secciones):

> Referencia visual: borde azul→rosa, fondo oscuro transparente, texto blanco en negrita. Sin relleno.

```css
.btn-outline {
  display: inline-block;
  padding: 14px 32px;
  border: 2px solid transparent;
  border-radius: 8px;
  /* Técnica padding-box/border-box para borde degradado */
  background: linear-gradient(var(--bg), var(--bg)) padding-box,
              var(--gradient) border-box;
  color: var(--text);
  font-weight: 600;
  font-size: 15px;
  text-decoration: none;
  cursor: pointer;
  transition: all 0.3s ease;
}
.btn-outline:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-accent);
}
```

**Ghost** (sin fondo, borde sutil morado):
```css
.btn-ghost {
  display: inline-block;
  padding: 14px 32px;
  background: transparent;
  border: 2px solid rgba(124, 58, 237, 0.3);
  border-radius: var(--radius);
  color: var(--text);
  font-size: 15px;
  font-weight: 500;
  text-decoration: none;
  cursor: pointer;
  transition: all 0.3s ease;
}
.btn-ghost:hover {
  border-color: rgba(124, 58, 237, 0.8);
  background: rgba(124, 58, 237, 0.1);
  transform: translateY(-2px);
}
```

---

## 9. Header / Navbar

```css
.site-header {
  position: sticky;
  top: 0;
  height: 64px;
  background: rgba(10, 10, 10, 0.95);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border);
  z-index: 100;
}
```

Los nav links usan `color: var(--text-secondary)` y al hover `color: var(--text)` + `background: var(--surface)`.

---

## 10. Footer

Separado del contenido con una línea degradada (no un borde sólido):

```css
.site-footer {
  background: var(--surface);
  padding: 40px 0;
  position: relative;
}
.site-footer::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: var(--gradient);
  opacity: 0.5;
}
```

---

## 11. Skeleton Loading

Para estados de carga. Usar en lugar de spinners:

```css
@keyframes skeleton-loading {
  0%   { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}

.skeleton {
  background: linear-gradient(
    90deg,
    var(--surface) 25%,
    var(--border-light) 50%,
    var(--surface) 75%
  );
  background-size: 200% 100%;
  animation: skeleton-loading 1.5s infinite;
  border-radius: 4px;
}
```

---

## 12. Animación de iconos flotantes (Hero)

```css
@keyframes float {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  50%       { transform: translateY(-20px) rotate(5deg); }
}

.floating-icon {
  width: 60px;
  height: 60px;
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: rgba(255,255,255,0.4);
  backdrop-filter: blur(10px);
  animation: float 6s ease-in-out infinite;
}
/* Escalonar los delays: 0s, 0.5s, 1s, 1.5s, 2s, 2.5s */
```

---

## 13. Íconos sociales (Footer)

```css
.icon-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 44px;
  height: 44px;
  border-radius: 50%;
  background: var(--card-bg);
  border: 1px solid var(--border);
  color: var(--text-secondary);
  text-decoration: none;
  transition: all 0.2s ease;
}
.icon-link:hover {
  color: var(--accent);
  border-color: var(--accent);
  transform: translateY(-2px);
}
```

---

## 14. Accesibilidad

Siempre incluir:

```css
:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 2px;
}
```

---

## 15. Badges numerados (insight numbers)

Para numerar items en cards (1, 2, 3…) usar borde degradado sin relleno, igual que `btn-outline`. Nunca fondo sólido ni gradiente relleno.

```css
.ibadge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px; height: 32px;
  border-radius: 50%;
  border: 1.5px solid transparent;
  background: linear-gradient(var(--card-bg), var(--card-bg)) padding-box,
              var(--gradient) border-box;
  color: var(--text-secondary);
  font-size: 13px; font-weight: 600;
  flex-shrink: 0;
  margin-bottom: 10px;
}
```

---

## 17. Iconografía

**Regla principal:** Los iconos deben ser **de un solo color** (monocromáticos). Evitar emojis con colores propios (🔷, 🛍️, 📊, etc.) porque rompen la coherencia visual del dark mode.

**Opciones preferidas (de mayor a menor preferencia):**
1. **SVG inline monocromático** — `currentColor` para heredar el color del contexto.
2. **Unicode neutros** — símbolos sin color propio: `◆`, `◇`, `▸`, `→`, `✦`, `⬡`, `○`, `●`.
3. **Texto abreviado** — iniciales o siglas dentro de un chip estilizado.

**Nunca usar:** emojis con paleta de color propia en badges, tags, chips o iconos de interfaz. Solo se permite en contenido decorativo secundario (bullets de listas, hints de teclado) donde el color no afecta la coherencia visual.

**Color de iconos monocromáticos:**
- Por defecto: `color: var(--text-secondary)` (#b0b0b0)
- En hover o estado activo: `color: var(--text)` o `color: var(--accent)`
- En chips/badges de color: heredar el color del propio chip

---

## 18. Links de texto

Los links inline (`<a>`) **no usan color de acento (morado)**. El morado/gradiente es exclusivo para botones y elementos de UI destacados, no para links de texto.

| Contexto | Color por defecto | Color hover |
|----------|-------------------|-------------|
| Links en cards / autor | `var(--text-secondary)` | `var(--text)` |
| Links en cuerpo de texto | `var(--text-secondary)` | `var(--text)` |
| Botones/CTAs | gradiente o `var(--accent)` | — |

```css
a {
  color: var(--text-secondary);
  text-decoration: none;
  transition: color 0.2s ease;
}
a:hover {
  color: var(--text);
}
```

---

## Instrucciones de aplicación

Al invocar este skill en un nuevo proyecto:

1. **Analiza el proyecto** — detecta qué tecnología usa (HTML/CSS puro, React, Next.js, Vue, etc.)
2. **Adapta los tokens** — si usa Tailwind, convierte las variables a `tailwind.config.js`. Si usa CSS Modules, créalos apropiadamente. Si es HTML/CSS puro, crea un `styles.css` con las variables en `:root`.
3. **No elimines funcionalidad existente** — solo aplica el estilo encima del contenido actual.
4. **Respeta la jerarquía de fondos** — alterna `--bg` y `--surface` entre secciones.
5. **Aplica el gradiente con criterio** — solo en elementos destacados: texto hero, botones primarios, línea del footer, bordes activos. No en todo.
6. **Pregunta si hay dudas** sobre qué secciones priorizar antes de escribir código.
