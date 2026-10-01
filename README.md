# Reto #3 - Menú de Navegación Animado

Menú de navegación moderno y horizontal con efectos visuales llamativos, construido **solo con HTML y CSS**.
El enfoque principal es el uso de **transiciones y transformaciones** para lograr interacciones suaves. El menú es responsivo y accesible.

## Estructura

```
/menu-animado/
|-- index.html   (Estructura del menú)
|-- styles.css   (Estilos y animaciones)
```

- `index.html`: encabezado con el logo y el menú (`<header>`, `<nav>`, `<ul>`), secciones de contenido (`<main>`, `<section>`) y pie de página (`<footer>`).
- `styles.css`: variables, estilos base, menú horizontal, animaciones, indicador activo, media queries y accesibilidad.

## Características implementadas

| Característica | Cómo se logra |
| --- | --- |
| Subrayado deslizante en hover | Pseudo-elemento `::after` con `transform: scaleX(0)` → `scaleX(1)` y `transition`. Cambiando `transform-origin` la línea entra por la izquierda y sale por la derecha. |
| Transformaciones al interactuar | En `:hover` y `:focus-visible` el enlace cambia de color y de fondo, y crece con `transform: translateY(-2px) scale(1.05)`. En `:active` se encoge con `scale(0.97)`. |
| Indicador activo sin JavaScript | `:target` (combinado con `:has()`) deja marcado el enlace de la sección que aparece en la URL. `:focus-within` marca el elemento del menú que tiene el foco. Sin `#id` en la URL, "Inicio" aparece activo. |
| Diseño responsivo | Mobile-first: logo y menú apilados y centrados. Desde `768px`, logo a la izquierda y menú a la derecha. Por debajo de `400px` los enlaces son más compactos. |
| Semántica y accesibilidad | Etiquetas HTML5, `aria-label` en el `<nav>`, `aria-labelledby` en cada sección, foco visible con `outline` y respeto de `prefers-reduced-motion`. |
| Estética clara y moderna | Tipografía del sistema, espaciado uniforme y una paleta de colores armoniosa definida en variables CSS. |

## Variables principales

| Variable | Valor | Uso |
| --- | --- | --- |
| `--color-primario` | `#4f46e5` | Subrayado, enlace activo y hover |
| `--color-primario-suave` | `#eef2ff` | Fondo del enlace en hover |
| `--duracion` | `0.3s` | Duración de todas las transiciones |
| `--curva` | `cubic-bezier(0.4, 0, 0.2, 1)` | Curva de aceleración de las transiciones |
| `--subrayado-grosor` | `2px` | Grosor de la línea animada |

Todas las transiciones usan `--duracion`. Con movimiento reducido vale `0s`, así se desactivan desde un solo lugar.

## Cómo probarlo

1. Abrir `index.html` en el navegador.
2. Pasar el cursor sobre un enlace: la línea se desliza debajo y el enlace cambia de color, de fondo y de tamaño.
3. Hacer clic en un enlace: la página baja hasta la sección, la URL cambia (por ejemplo `#servicios`) y ese enlace queda marcado como activo.
4. Navegar con `Tab`: el enlace con foco muestra el contorno y el subrayado.
5. Reducir el ancho de la ventana por debajo de 768px: el logo queda arriba y el menú debajo, centrado.

## Autor

ujuanpolanco
