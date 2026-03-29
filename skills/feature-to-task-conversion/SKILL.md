---
name: feature-to-task-conversion
description: Splits a gameplay feature into brief-sized tasks with clear ownership, dependencies, deliverables, and acceptance criteria for this repo. Use when moving from specs to execution or when the orchestrator needs an implementable backlog chunk.
---

# Feature → task conversion

## Objetivo

Convertir un **feature** (puede ser grande) en **tareas** que encajen en `templates/task_brief.md`: una tarea ejecutable por iteración, sin mezclar tres features en un solo brief.

## Pasos

1. Nombrar el feature y su **ID** sugerido (`FEAT-…` o referencia a `MEC-…`).
2. Listar **resultado integrado** del feature (qué puede probar Camilo al cerrar todas las tareas).
3. Partir en tareas donde cada una tenga:
   - **un ejecutor primario** (Cursor repo vs doc-only subagent)
   - **entregables** concretos (archivos, BPs nombrados, o doc en ruta)
   - **dependencias** explícitas (TASK B después de TASK A)
   - **criterios de aceptación** copiables al brief
4. Marcar tareas **bloqueadas** por decisiones de Camilo (escala a PO, no inventar).
5. Dejar **una** tarea de “integración mínima” si el feature cruza varios sistemas (smoke del loop).

## Anti-patrones

- Un brief que dice “hacer todo el combate”.
- Dos personas/agentes tocando el mismo asset crítico sin orden definido.
- Criterios subjetivos (“se siente bien”) sin observables (“enemigo muere en X hits con valores por defecto”).
