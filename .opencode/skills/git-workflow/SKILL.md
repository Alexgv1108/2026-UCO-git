---
name: Flujo de trabajo con Git
description: Guía el ciclo de trabajo con Git del curso (estado, staging, commit, ramas y push) usando Conventional Commits. Úsala al preparar commits, crear o cambiar de rama, subir cambios o resolver dudas del flujo.
---

# Flujo de trabajo con Git

Flujo estándar del repositorio **2026-UCO-git**. Síguelo en orden y confirma
cada paso destructivo con el usuario.

## Ciclo diario

1. **Ver estado** antes de tocar nada:
   ```sh
   git status
   git log --oneline -5
   ```
2. **Preparar** solo lo que va en el commit:
   ```sh
   git add <archivos>
   git diff --staged        # revisa antes de commitear
   ```
3. **Commitear** con un mensaje Conventional Commits (ver
   `references/conventional-commits.md`):
   ```sh
   git commit -m "docs: agregar párrafo de prueba en index.html"
   ```
4. **Subir** la rama:
   ```sh
   git push -u origin <rama>
   ```

## Ramas

- La rama principal es `main`; el trabajo se hace en ramas descriptivas.
- Nombres en kebab-case: `feature/menu-navegacion`, `fix/alt-imagenes`,
  `docs/readme`.
- Ver `references/ramas.md`.

## Reglas del curso

- Un commit = un cambio lógico. Evita mezclar HTML, estilos y docs.
- Nunca `git push --force` sobre `main`.
- Antes de un `reset --hard` o `clean`, muestra qué se va a perder.

## Errores frecuentes

| Síntoma | Solución segura |
| --- | --- |
| Preparé un archivo por error | `git restore --staged <archivo>` |
| Edité y quiero descartar | `git restore <archivo>` |
| Commit con mensaje malo (no subido) | `git commit --amend` |
| Commit ya subido | `git revert <hash>` (no reescribir historia) |
