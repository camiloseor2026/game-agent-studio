---
name: project-management
description: Sequences work packages, maps dependencies, defines handoffs, and keeps scope aligned to sprint boundaries for this game-dev studio repo. Use when planning sprints, breaking down goals, ordering tasks, or preventing parallel work that breaks integration.
---

# Project management (Game Agent Studio)

## Objetivo

Traducir intención de producto en **tareas ordenadas**, con **dependencias explícitas**, **handoffs claros** y **un ejecutor primario** por paquete, sin inflar alcance.

## Principios

1. **Un brief = una tarea ejecutable** (`templates/task_brief.md`). Si no cabe, partir.
2. **Grafo de dependencias antes de fechas**: qué bloquea qué; luego estimación liviana (orden, no Gantt pesado salvo que Camilo pida).
3. **WIP bajo en la misma superficie**: misma carpeta del repo, mismo sistema UE o mismo contrato → **secuencial**, no dos briefs paralelos que choquen.
4. **Handoff explícito**: cada salida usa `templates/agent_output.md` con “Para Cursor / Orquestador / Camilo”.
5. **Scope gate**: todo paquete incluye “Fuera de alcance”. Contradicción con `PROJECT_CHARTER.md` → escalar a Camilo, no seguir descomponiendo.

## Checklist al planificar

- [ ] ¿Prioridad viene de Camilo o del charter/sprint activo?
- [ ] ¿Cada ítem tiene ID (`TASK-…` / `TASK-Sxx-…`) y criterios de aceptación?
- [ ] ¿Dependencias escritas (A antes que B)?
- [ ] ¿Un solo subagente “dueño” por paquete (salvo doc puramente transversal)?
- [ ] ¿Validación/QA encajada **después** de entregables integrables, no antes de existir nada que probar?

## Salida típica del orquestador

- Lista ordenada (tabla o lista numerada): tarea → depende de → entregable → ejecutor previsto.
- Referencias a rutas de docs del repo (`docs/sprint_01_execution_plan.md`, `docs/roadmap/`, etc.).

## Alineación entre “equipos”

Los equipos son **roles** (subagentes), no silos en conflicto:

- El orquestador **serializa** lo que toca el mismo binario/repo/escena.
- **Research (Market)** y **LiveOps** pueden alimentar briefs tempranos, pero no deben duplicar ownership de implementación de Gameplay/World/Art.
