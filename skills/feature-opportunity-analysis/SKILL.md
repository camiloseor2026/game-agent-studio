---
name: feature-opportunity-analysis
description: Turns market and benchmark insights into prioritized feature opportunities with rationale, risks, and fit to the current charter and slice. Use when translating research into backlog hints for the orchestrator or Camilo.
---

# Feature opportunity analysis

## Objetivo

Puente entre **insight** y **decisión de producto**: qué features valen la pena explorar en el slice o en backlog, sin escribir specs de implementación.

## Salida

Tabla:

| Oportunidad (nombre corto) | Insight que la sostiene | Encaje charter/slice | Esfuerzo relativo (S/M/L) | Riesgo principal | Recomendación (explorar / posponer / descartar) |

## Reglas

1. Cada fila enlaza a **benchmark** o **trend cluster** o **audiencia** (referencia ID o sección).
2. **Descartar** con razón explícita cuenta como valor (evita scope creep).
3. **Explorar** implica siguiente paso: pregunta para Gameplay, experimento de UX, o playtest — una línea.
4. No duplicar owner de **Gameplay**; tú propones **prioridad y porqué**; el orquestador convierte en TASKs.

## Límites

- No estimar **meses-hombre** finos sin mandato; S/M/L es suficiente al inicio.
- LiveOps/monetización: solo fila conceptual si el charter no abrió fase.
