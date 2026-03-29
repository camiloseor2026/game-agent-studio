# Orquestador — definición en repo

## Dónde vive qué

| Qué | Ruta canónica (versionar aquí) | Cursor |
|-----|-------------------------------|--------|
| Subagente (prompt + frontmatter) | `agents/orchestrator/orchestrator.md` | Enlaza desde `.cursor/agents/orchestrator.md` → este archivo |
| Skills del orquestador | `skills/project-management/`, `skills/game-dev-lifecycle/` | Enlaza desde `.cursor/skills/<nombre>/` → esas carpetas |

Cursor **solo** descubre subagentes bajo `.cursor/agents/` y skills bajo `.cursor/skills/`. Por eso el repo usa **enlaces simbólicos**: editas en `agents/` y `skills/`; Cursor sigue viendo los mismos archivos.

Si clonas en Windows, verifica que Git tenga `core.symlinks=true` y permisos de administrador si hace falta; si no, copia manualmente o regenera los symlinks según `../README.md`.

## Artefactos adicionales

Planes, estado de sprint y outputs consolidados pueden ir en esta carpeta o en `docs/` según `AGENT_SYSTEM.md`.
