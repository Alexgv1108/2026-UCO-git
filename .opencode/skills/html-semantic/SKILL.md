---
name: HTML semántico
description: Aplica estructura HTML5 semántica y buenas prácticas al crear o editar páginas web. Úsala al escribir o revisar cualquier archivo .html.
---

# HTML semántico

Guía para escribir HTML claro, válido y bien estructurado en este proyecto.

## Plantilla base

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Documento</title>
  </head>
  <body>
    <header>
      <h1>Título principal</h1>
      <nav><!-- enlaces de navegación --></nav>
    </header>

    <main>
      <section>
        <h2>Sección</h2>
        <p>Contenido…</p>
      </section>
    </main>

    <footer><!-- pie de página --></footer>
  </body>
</html>
```

## Reglas

- Un solo `<h1>` por página; no saltes niveles (`h1` → `h3`).
- Usa etiquetas por **significado**, no por apariencia: `strong`/`em`, no
  `b`/`i` para énfasis real.
- `lang="es"` en `<html>` (o el idioma correcto).
- Indenta con 2 espacios y cierra todas las etiquetas.
- Rutas relativas para recursos locales (`./styles.css`, `./img/logo.png`).

## Revisión rápida

- [ ] `<!DOCTYPE html>`, `lang`, `charset`, `viewport`, `title`.
- [ ] Estructura con `header` / `nav` / `main` / `section` / `footer`.
- [ ] Jerarquía de encabezados coherente.
- [ ] Sin etiquetas sin cerrar ni atributos mal escritos.

Ver `references/checklist.md` para la lista completa.
