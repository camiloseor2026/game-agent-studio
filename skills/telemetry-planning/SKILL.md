---
name: telemetry-planning
description: Plans conceptual telemetry for games: questions to answer, event categories, privacy boundaries, and funnel stages without locking a vendor or SDK. Use when defining what to learn from playtests or future live builds.
---

# Telemetry planning

## Objetivo

Pasar de “queremos datos” a **preguntas de producto** → **eventos o agregados** → **límites éticos**.

## Salida

1. **Preguntas** (máx. 5–10): ej. “¿Dónde abandonan el primer mapa?”
2. **Embudo** simplificado: install → first session → core loop complete → return D1/D7 (marcar N/A si slice).
3. **Taxonomía conceptual de eventos**:
   - `session_start` / `session_end` (ejemplo)
   - `core_loop_*` alineados a mecánicas del slice
   - `error` / `perf` si aplica
4. **Dimensiones** permitidas (versión build, mapa, plataforma) vs **prohibidas** (PII sin base legal).
5. **Dashboard imaginario**: 3–5 gráficos que contestarían las preguntas (sin herramienta fija).
6. **Implementación**: “hook en UE / servidor / repo” como **siguiente brief**, no en esta skill.

## Reglas

- Etiquetar cada ítem como **must-have slice** vs **post-slice**.
- Si no hay red, definir **telemetría local o export manual** para playtests.
