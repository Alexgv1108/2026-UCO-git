# Configuración de OpenCode — proyecto `2026-UCO-git`

Configuración de OpenCode (V2) para este repositorio de práctica de **Git +
HTML**. Todo vive dentro de `.opencode/` y se descubre automáticamente al usar
OpenCode en este proyecto.

## Agentes

Definidos en `.opencode/agents/`. Invócalos pidiéndolos por su nombre o
cámbialos con el selector de agente.

| Agente | Modo | Para qué sirve | Permisos |
| --- | --- | --- | --- |
| `orchestrator` | primary | **Agente por defecto.** Analiza la petición, la reparte entre los demás agentes y sintetiza el resultado. No edita ni ejecuta nada. | Solo delegar (`subagent`) |
| `git-tutor` | all | Explica Git, revisa el historial y guía el flujo paso a paso. No modifica nada. | Solo comandos `git` de lectura |
| `web-reviewer` | subagent | Revisa HTML/CSS/JS: errores, semántica y accesibilidad. Read-only. | Solo lectura |
| `commit-writer` | subagent | Redacta el mensaje de commit (Conventional Commits) desde el diff preparado. | Solo lectura + `git diff/log` |

El **orchestrator** se ejecuta por defecto (`default_agent` en `opencode.jsonc`).
Enruta así: Git → `git-tutor`; revisión web → `web-reviewer`; commits →
`commit-writer`; explorar código → `explore`; crear/editar/ejecutar →
`general`.

Usar un subagente directamente, por ejemplo:

```text
Usá el subagente web-reviewer para revisar prueba1/index.html
```

## Skills

Definidas en `.opencode/skills/<id>/SKILL.md` (con archivos de apoyo en
`references/`). Se cargan con la herramienta `skill` cuando son relevantes, o
mencionándolas como `@skill-id`.

| Skill (ID) | Descripción |
| --- | --- |
| `git-workflow` | Ciclo de Git del curso: estado, staging, commit, ramas y push + Conventional Commits. |
| `html-semantic` | Estructura HTML5 semántica, plantilla base y checklist. |
| `web-accessibility` | Buenas prácticas de accesibilidad (a11y) para HTML. |

## Comandos

Definidos en `.opencode/commands/`. Se lanzan escribiendo `/` en el TUI.

| Comando | Qué hace |
| --- | --- |
| `/commit` | Propone un mensaje de commit con Conventional Commits. |
| `/estado` | Resume el estado del repositorio en lenguaje claro. |
| `/revisar-web [archivos]` | Revisa HTML/CSS por errores, semántica y accesibilidad. |

## Configuración (`opencode.jsonc`)

- `formatter: true` → formatea HTML/CSS/JS al editarlos.
- `permissions` → los comandos destructivos (`git push`, `git reset --hard`,
  `git clean`, `rm -rf`, …) piden confirmación; el resto se permite.

## Estructura

```text
.opencode/
├── opencode.jsonc            # configuración del proyecto
├── README.md                 # este índice
├── agents/
│   ├── orchestrator.md
│   ├── git-tutor.md
│   ├── web-reviewer.md
│   └── commit-writer.md
├── commands/
│   ├── commit.md
│   ├── estado.md
│   └── revisar-web.md
└── skills/
    ├── git-workflow/
    │   ├── SKILL.md
    │   └── references/
    │       ├── conventional-commits.md
    │       └── ramas.md
    ├── html-semantic/
    │   ├── SKILL.md
    │   └── references/
    │       └── checklist.md
    └── web-accessibility/
        └── SKILL.md
```

## Añadir más

- **Nuevo agente**: crea `.opencode/agents/<nombre>.md` con frontmatter
  (`description`, `mode`, `model`, `permissions`) y el prompt en el cuerpo.
- **Nueva skill**: crea `.opencode/skills/<id>/SKILL.md`. El `id` es el nombre
  de la carpeta; añade `description` para que el modelo la descubra.
- **Nuevo comando**: crea `.opencode/commands/<nombre>.md`; el cuerpo es la
  plantilla y acepta `$ARGUMENTS`.
