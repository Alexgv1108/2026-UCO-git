# Ramas (referencia)

- `main`: rama estable. No se trabaja directamente en ella.
- Ramas de trabajo con prefijo por propósito:
  - `feature/<tema>` — nueva funcionalidad o sección.
  - `fix/<tema>` — corrección puntual.
  - `docs/<tema>` — documentación.
  - `chore/<tema>` — mantenimiento o configuración.

## Comandos útiles

```sh
git branch                    # listar ramas locales
git switch -c feature/menu    # crear y cambiar a una rama nueva
git switch main               # volver a main
git merge feature/menu        # fusionar una rama (desde main)
git branch -d feature/menu    # borrar rama ya fusionada
git push -u origin feature/menu
```

## Reglas

- Nunca borres una rama con `-D` sin confirmar que su trabajo está fusionado.
- Antes de fusionar, actualiza `main` con `git pull`.
