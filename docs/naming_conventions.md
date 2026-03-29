# Naming conventions

Objetivo: que Camilo, ChatGPT y Cursor encuentren cosas sin adivinar.

## Repo y ramas

- Carpetas: `snake_case` o `kebab-case` según carpeta existente del repo; **no mezclar** dentro del mismo nivel.
- Ramas: `feature/TASK-001-shooter-hud` (ID del brief + slug corto).

## Documentación

- Archivos: `MAYUS_UNDERSCORE.md` solo en raíz acordada (`PROJECT_CHARTER.md`); en `docs/`: `kebab-case.md` o `snake_case.md` — **preferir `snake_case.md`** en este repo para nuevos docs.
- Task IDs: `TASK-###` secuencial o por sprint (`TASK-S01-003`).

## Unreal (cuando exista el proyecto)

- **Maps:** `L_<Area>_<Variante>` (ej. `L_Greybox_Arena01`).
- **Blueprints:** `BP_<Sistema>_<Nombre>` (ej. `BP_Weapon_Pistol`).
- **Assets genéricos:** prefijo por tipo (`SM_`, `SK_`, `T_`, `M_`) según guía UE del equipo; documentar la tabla en este archivo cuando se fije la versión de engine.

## Agentes y prompts

- Carpeta agente: coincide con `agents/` (`gameplay`, `world`, `art_rigging`, etc.).
- Prompts: `prompts/<agente>_<tema>.md` o `.txt` (ej. `prompts/qa_smoke_checklist.md`).

## Commits

- Prefijos opcionales: `docs:`, `chore:`, `agents:`, `templates:` — sin código de gameplay hasta que el brief lo pida.
