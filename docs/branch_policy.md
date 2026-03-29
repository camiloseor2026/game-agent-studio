# Branch policy

Equipo: **Camilo** (PO), **ChatGPT** (arquitectura / planes), **Cursor** (cambios en repo).

## Ramas

| Rama | Uso |
|------|-----|
| `main` | Siempre desplegable / referencia; solo integración estable. |
| `develop` | (Opcional) integración continua entre features. |
| `feature/<TASK-id>-slug-corto` | Trabajo de una tarea o slice. |

Sin `develop`: las features pueden mergearse a `main` tras revisión de Camilo.

## Reglas

1. **Cursor** trabaja en `feature/*` salvo que Camilo pida hotfix puntual en rama dedicada (`hotfix/<slug>`).
2. **No force-push** a `main` (ni reescritura compartida sin acuerdo).
3. **PR o merge** a `main`: al menos revisión humana de Camilo; ChatGPT puede dejar review en comentarios / doc, no sustituye el OK del PO.
4. Commits: mensajes claros en imperativo (`add QA checklist`, `update agent brief template`).
5. Antes de merge: brief cumplido o explícitamente recortado en el PR.

## Flujo resumido

Camilo prioriza → brief en `templates/task_brief.md` (copiado con ID) → rama `feature/…` → Cursor implementa → PR → Camilo aprueba → merge a `main`.
