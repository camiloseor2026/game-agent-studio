---
name: game-dev-lifecycle
description: Orders game production phases for an incremental Unreal slice and maps work to Gameplay, World, Art/Rigging, QA, Market, and LiveOps subagent roles. Use when sequencing features, onboarding a new slice, or deciding what must exist before dependent systems.
---

# Ciclo de desarrollo (slice incremental, Unreal)

## Orden lógico por fases

Ajustar al sprint activo; en general **no saltar** dependencias duras.

1. **Fundamentos de producto y repo** — Visión, charter, convenciones, estructura UE, decisiones en `TECH_DECISIONS_LOG.md`. *Roles: Camilo, Orquestador, Cursor.*
2. **Vertical slice jugable (mínimo)** — Input, personaje, cámara, loop de combate básico, daño/muerte, un encounter simple. *Subagente primario: **Gameplay**; **World** greybox en paralelo solo si no compite por las mismas escenas/contratos.*
3. **Nivel y pacing** — Layout, navegación, encounters, documentación de mapa. *Subagente primario: **World**.*
4. **Arte y rig** — Placeholders consistentes, import pipeline, naming, LODs, rigs/animaciones stub. *Subagente primario: **Art/Rigging**.* Entra cuando el greybox y los requisitos de asset están claros.
5. **QA y validación** — Smoke, regresión, performance básica, criterios de aceptación por feature. *Subagente primario: **QA**.* Se **cierra el loop** tras bloques integrables; no sustituye prueba manual de Camilo en hitos.
6. **Mercado (paralelo seguro)** — Benchmarks, género, diferenciación; alimenta briefs, no bloquea el primer loop técnico. *Subagente: **Market**.*
7. **Live ops (diseño temprano)** — Telemetría conceptual, eventos, release checklist; sin implementación pesada hasta que el slice sea estable. *Subagente: **LiveOps**.*

## Qué hace cada subagente (recordatorio)

| Subagente | Enfoque | Típicamente después de… |
|-----------|---------|-------------------------|
| **Gameplay** | Loop, armas, input, daño, IA simple, integración BP/C++ | Fundamentos / contratos básicos del proyecto |
| **World** | Greybox, layout, encounters, pacing, doc de nivel | Dirección de slice + requisitos de gameplay mínimos |
| **Art/Rigging** | Pipeline, formatos, rig, anim placeholder, materiales base | Lista de assets y convenciones acordadas |
| **QA** | Planes de prueba, smoke, regresión, perf, taxonomía de bugs | Features “integrables” definidas en brief |
| **Market** | Investigación, benchmarks, insights para diseño/GTM | Puede arrancar temprano; entregables son docs/insights |
| **LiveOps** | Telemetría conceptual, operación, parches, retención | Slice o hito estable; antes solo hooks/documentación |

## Anti-caos (integración)

- **Gameplay + World**: si comparten la misma escena o blueprints críticos, el orquestador **ordena** (p. ej. contrato de “player + dummy enemy” antes de arte final de nivel).
- **Art antes de gameplay estable**: solo placeholders; no bloquear código por arte high-end en fase slice.
- **QA**: definir **cuándo** corre smoke (tras merge local o hito); no exigir suite completa antes del primer playable.

## Referencias en repo

- `AGENT_SYSTEM.md` — definición de subagentes.
- `docs/orchestrator_spec.md` — delegación y escalación.
- `PROJECT_CHARTER.md` — límites de fase (qué no hacer al inicio).
