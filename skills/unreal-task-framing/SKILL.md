---
name: unreal-task-framing
description: Translates task requests into Unreal Engine context using only project facts from the repo: naming conventions, logged engine version, and existing paths under unreal/. Use when any agent must describe UE work without inventing project layout or features.
---

# Unreal task framing (transversal)

## Objetivo

Evitar **improvisación** sobre el proyecto UE: solo lo que el repo y los docs confirman o lo que el brief declara explícitamente.

## Antes de escribir tareas o rutas UE

1. **`TECH_DECISIONS_LOG.md`** — versión de engine y decisiones registradas.
2. **`docs/naming_conventions.md`** — prefijos de mapas, BPs, assets.
3. **`unreal/`** — si existe `.uproject` y estructura; si no, decir **“proyecto UE pendiente”** y no inventar nombres de carpeta interna.
4. **Brief** — mapa, feature, o paths que Camilo ya aprobó.

## Al formular una tarea UE

- Separar **Editor / PIE / packaged** si afecta validación.
- No asumir **multiplayer**, **GAS**, **plugins** salvo que estén en charter o log.
- Para **gameplay** detallado (BP vs C++, módulos), cruzar con `skills/unreal-gameplay-task-framing/SKILL.md` cuando el agente sea Gameplay.

## Salida típica

Bullets: **precondiciones** → **acciones en UE o repo** → **verificación** → **riesgos** (sin paths inventados).
