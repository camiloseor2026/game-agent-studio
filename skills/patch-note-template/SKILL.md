---
name: patch-note-template
description: Structures player-facing and internal patch notes for game builds: version, highlights, fixes, known issues, and rollback notes. Use when shipping internal playtests, milestones, or documenting changes for the team.
---

# Patch note template

## Objetivo

Comunicación **clara y trazable** entre build y quien lo consume (equipo o testers).

## Plantilla — jugadores / testers

```markdown
## [Build / versión] — [fecha]

### Destacados
- …

### Correcciones
- …

### Balance / diseño
- …

### Conocidos
- …

### Notas de instalación
- …
```

## Plantilla — interno (equipo)

```markdown
## [Build] — changelog técnico

**Rama / commit:** …
**Áreas tocadas:** Gameplay | World | Art | Build | Tooling

### Cambios
- …

### Migración / datos
- …

### Riesgo de regresión
- …

### Rollback
- …
```

## Reglas

- Un bullet = un cambio observable cuando sea posible.
- **Known issues** obligatorio si hay bugs aceptados para el hito.
- Alinear numeración con **TASK ID** o tag si el repo lo usa.
