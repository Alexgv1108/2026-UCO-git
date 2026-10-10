---
name: Accesibilidad web
description: Buenas prácticas de accesibilidad (a11y) para HTML: idioma, texto alternativo, contraste, foco y navegación por teclado. Úsala al crear o revisar interfaces para que todos puedan usarlas.
---

# Accesibilidad web (a11y)

Pautas básicas (inspiradas en WCAG) aplicables a los ejercicios HTML del curso.

## Fundamentos

1. **Idioma**: `<html lang="es">` para que los lectores de pantalla pronuncien
   bien.
2. **Texto alternativo**: toda `<img>` necesita `alt` descriptivo; usa `alt=""`
   solo si es puramente decorativa.
3. **Estructura**: encabezados jerárquicos y etiquetas semánticas dan contexto
   a los lectores de pantalla y a la navegación por teclado.
4. **Formularios**: `<label for="id">` asociado a cada `<input id="id">`. No
   uses el `placeholder` como única etiqueta.
5. **Contraste**: texto sobre fondo con relación mínima 4.5:1 (texto normal).
6. **Foco visible**: no elimines el contorno de foco (`outline`) sin reemplazo.
7. **Color**: no transmitas información **solo** con color (añade texto o
   iconos).

## Navegación por teclado

- Todo elemento interactivo debe poder alcanzarse con `Tab`.
- El orden del DOM debe coincidir con el orden visual.
- Evita `tabindex` con valores positivos.

## Cómo revisar

- Recorre la página solo con `Tab` y comprueba que siempre ves dónde estás.
- Ejecuta un chequeo automático (por ejemplo la extensión axe DevTools) y
  corrige lo que reporte.
- Pregunta: "¿alguien que no ve la pantalla puede entender y usar esto?"
