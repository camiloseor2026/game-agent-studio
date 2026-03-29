---
name: acceptance-criteria-validation
description: Validates deliverables against acceptance criteria from task briefs and specs, marking pass, fail, or blocked with evidence. Use when closing a task, reviewing PR scope, or reconciling agent output with templates.
---

# Acceptance criteria validation

## Objetivo

Convertir criterios del brief en **veredictos binarios** + **gaps documentados**.

## Proceso

1. Copiar criterios numerados del `templates/task_brief.md` (o spec referenciada).
2. Por cada criterio: **Pass** | **Fail** | **Blocked** | **N/A** con **evidencia** (captura, log, ruta de archivo, pasos de repro).
3. Si un criterio es subjetivo, proponer **criterio observable** sustituto para el siguiente sprint (nota, no reescribir el brief solo).
4. Listar **criterios faltantes** en el brief que impedían validar (deuda de proceso).

## Salida

Tabla:

| # Criterio (texto corto) | Estado | Evidencia | Notas |
|--------------------------|--------|-----------|-------|

Resumen: **X/Y pass**; bloqueos → Camilo u Orquestador.

## Límites

- No “aprobar” alcance nuevo no listado en el brief; eso es **hallazgo de scope creep**.
