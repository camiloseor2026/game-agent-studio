---
name: smoke-checklist-generation
description: Generates minimal reproducible smoke checklists for Unreal builds, vertical slices, or repo milestones. Use before internal playtests, after merge to main, or when defining what must always work in PIE.
---

# Smoke checklist generation

## Objetivo

Lista **corta y ordenada** de pasos que demuestran que el build no está roto en lo esencial del slice.

## Reglas

- Máximo **10–15 pasos** salvo que Camilo pida exhaustivo; smoke ≠ regresión completa.
- Cada paso: **acción** → **resultado esperado** observable (no “se siente bien”).
- Incluir: arranque editor/proyecto, mapa de prueba, input básico, un flujo del core loop si existe.
- Marcar **N/A** explícito si el sistema aún no existe (no fallar en silencio).
- Versión: fecha o TASK ID en cabecera del checklist.

## Plantilla

```markdown
# Smoke — [proyecto / hito] — [fecha o TASK-ID]

## Precondiciones
- Build / branch: …
- Mapa: …

## Pasos
| # | Acción | Resultado esperado | Pass/Fail |
|---|--------|-------------------|-----------|
| 1 | … | … | |
```

## Salida

Markdown listo para `docs/qa/` o pegar en comentario de PR / `agent_output`.
