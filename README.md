# Claude Skills

Colección de skills portables para Claude Code. Cada skill es un slash command personalizado que extiende las capacidades de Claude para agilizar tareas de desarrollo recurrentes.

## ¿Qué es un skill?

Un skill es una carpeta que contiene un archivo `SKILL.md` con instrucciones especializadas. Claude Code los detecta automáticamente y los expone como comandos invocables durante cualquier conversación.

## Skills disponibles

| Skill | Descripción |
|-------|-------------|
| `datablog-design-v1` | Aplica el sistema de diseño personal (dark mode, gradiente azul→morado→rosa, cards, skeleton loading) a cualquier proyecto. |

## Estructura

```
skills/
├── README.md
└── nombre-del-skill/
    └── SKILL.md        # Definición del skill (frontmatter + instrucciones)
```

Cada `SKILL.md` incluye:
- **Frontmatter** (`name`, `description`) — metadatos que Claude usa para identificar cuándo invocar el skill.
- **Cuerpo** — instrucciones detalladas que Claude sigue al ejecutarlo.

## Uso

Desde cualquier conversación con Claude Code, invoca un skill con:

```
/nombre-del-skill
```

## Agregar un nuevo skill

1. Crea una carpeta con el nombre del skill dentro de `.claude/skills/`.
2. Añade un archivo `SKILL.md` con el siguiente formato:

```markdown
---
name: nombre-del-skill
description: Descripción breve de cuándo y para qué usarlo.
---

# Nombre del Skill

Instrucciones detalladas para Claude...
```

3. El skill queda disponible de inmediato en Claude Code.
