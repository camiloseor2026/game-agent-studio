# Naming Conventions

Objetivo: que Camilo y quien ejecute con Cursor encuentren cosas sin adivinar, alineado a lo documentado por el orquestador en `docs/`.

## General rule
- Preferir nombres claros, cortos y consistentes.
- No mezclar estilos dentro del mismo grupo de archivos o carpetas.
- Evitar abreviaturas ambiguas.

## Repository folders
- Para nuevas carpetas del repo, usar `snake_case`.
- Mantener nombres ya existentes si el repo ya los creó de otra forma y no vale la pena refactorizar.
- Ejemplos:
  - `docs`
  - `agents`
  - `art_rigging`
  - `live_ops`

## Branches
- Formato recomendado:
  - `feature/TASK-001-short-slug`
  - `docs/short-slug`
  - `research/short-slug`
  - `hotfix/short-slug`

Ejemplos:
- `feature/TASK-001-shooter-hud`
- `docs/branch-policy-update`
- `research/shooter-market-scan`

## Documentation
- En la raíz del repo, usar `UPPER_SNAKE_CASE.md` para documentos fundacionales acordados.
- Ejemplos:
  - `PROJECT_CHARTER.md`
  - `AGENT_SYSTEM.md`
  - `SPRINT_01_BACKLOG.md`
  - `TECH_DECISIONS_LOG.md`

- En `docs/`, usar `snake_case.md` para todos los nuevos documentos.
- Ejemplos:
  - `branch_policy.md`
  - `naming_conventions.md`
  - `qa_workflow.md`

## Task IDs
- Formato base: `TASK-###`
- Formato por sprint si aplica: `TASK-S01-003`

## Templates
- En `templates/`, usar `snake_case.md`
- Ejemplos:
  - `task_brief.md`
  - `agent_output.md`

## Prompts
- En `prompts/`, usar:
  - `<agent>_<topic>.md`
- Ejemplos:
  - `qa_smoke_checklist.md`
  - `gameplay_weapon_prompt.md`
  - `world_graybox_prompt.md`

## Agents
- Cada carpeta debe coincidir con el nombre del agente en `agents/`
- Ejemplos:
  - `agents/gameplay`
  - `agents/world`
  - `agents/art_rigging`
  - `agents/qa`
  - `agents/market`
  - `agents/live_ops`

## Unreal conventions
Estas reglas aplican cuando exista el proyecto Unreal.

### Maps
- `L_<Area>_<Variant>`
- Ejemplo:
  - `L_Greybox_Arena01`

### Blueprints
- `BP_<System>_<Name>`
- Ejemplos:
  - `BP_Weapon_Pistol`
  - `BP_Enemy_Grunt`
  - `BP_GameMode_Shooter`

### Core asset prefixes
- `SM_` = Static Mesh
- `SK_` = Skeletal Mesh
- `T_` = Texture
- `M_` = Material
- `MI_` = Material Instance
- `ABP_` = Animation Blueprint
- `A_` = Animation
- `SFX_` = Sound effect
- `UI_` = UI asset or widget-related asset

Si luego definimos una guía más completa por versión de Unreal, este archivo se amplía.

## Scripts and tools
- Usar `snake_case`
- Ejemplos:
  - `validate_assets.py`
  - `build_smoke_check.sh`

## Commits
- Mensajes cortos, claros y en imperativo.
- Prefijos opcionales:
  - `docs:`
  - `chore:`
  - `agents:`
  - `templates:`
  - `research:`

Ejemplos:
- `docs: refine branch policy`
- `templates: update agent output`
- `agents: add qa handoff template`