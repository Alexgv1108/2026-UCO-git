---
description: Redacta un mensaje de commit con Conventional Commits a partir de lo preparado
agent: commit-writer
subagent: true
---

Revisa los cambios preparados con `git status` y `git diff --staged` y propone
un mensaje de commit siguiendo Conventional Commits.

Devuelve únicamente:

1. El mensaje propuesto en un bloque de código.
2. La lista de archivos incluidos.

No ejecutes el commit; solo propón.
