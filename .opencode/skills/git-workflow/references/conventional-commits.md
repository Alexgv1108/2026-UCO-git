# Conventional Commits (referencia)

Formato del asunto:

```
<tipo>(<alcance opcional>): <descripción>
```

- Imperativo, en español, minúscula inicial, sin punto final, ≤ 72 caracteres.

## Tipos

| Tipo | Uso |
| --- | --- |
| `feat` | Nueva funcionalidad o contenido |
| `fix` | Corrección de un error |
| `docs` | Cambios solo en documentación (README, comentarios) |
| `style` | Formato, espacios, indentación (sin cambiar lógica) |
| `refactor` | Reestructura sin cambiar comportamiento |
| `test` | Añadir o ajustar pruebas |
| `chore` | Tareas de mantenimiento (config, dependencias) |

## Ejemplos

```
feat(nav): agregar menú de navegación
fix(html): cerrar la etiqueta <p> faltante
docs: crear README con instrucciones del proyecto
style(index): indentar el HTML con 2 espacios
chore: configurar OpenCode del curso
```

## Cuerpo y pie

- Separa el asunto del cuerpo con **una línea en blanco**.
- El cuerpo explica el **por qué**, no el qué (el diff ya dice el qué).
- Referencia issues/PR con `Refs: #12` si aplica.
