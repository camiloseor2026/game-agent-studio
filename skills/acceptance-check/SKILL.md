---
name: acceptance-check
description: Validates work against acceptance criteria from the task brief with pass, fail, blocked, or N/A plus evidence. Use when closing any task, reviewing deliverables, or before marking agent output complete.
---

# Acceptance check

## Objetivo

Cierre **binario** frente a los criterios del brief, sin criterios nuevos no acordados.

## Proceso

1. Enumerar los **criterios de aceptación** del brief (copiar textos o IDs si existen).
2. Por cada uno: **Pass** | **Fail** | **Blocked** | **N/A** + **evidencia** (ruta de archivo, paso de prueba, captura descrita).
3. Si un criterio es **subjetivo**, proponer observables para la **siguiente** iteración (nota, no cambiar el brief solo).
4. Resumen: **X/Y pass**; lista de **Fails** con severidad sugerida.

## Relación con QA

Para profundidad en taxonomía y plantillas de bug, usar también `skills/acceptance-criteria-validation/SKILL.md` cuando el agente sea QA o el hito lo exija.

## Scope

No sustituye **aprobación de Camilo**; alimenta la decisión y el `structured-handoff`.
