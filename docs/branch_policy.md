# Branch Policy

Equipo: **Camilo** (PO / decisión final), **Orquestador y subagentes** (flujo y documentación interna), **Cursor** (ejecución local en el repo según brief).

## Branches

| Branch | Uso |
|--------|-----|
| `main` | Rama estable y referencia principal del proyecto. Solo cambios revisados e intencionales. |
| `develop` | Opcional. Úsese solo si el volumen de features crece y se necesita integración intermedia. |
| `feature/<TASK-id>-short-slug` | Trabajo funcional de una tarea o slice. |
| `docs/<short-slug>` | Cambios solo de documentación o templates. |
| `research/<short-slug>` | Investigación, benchmarks o análisis sin impacto directo en gameplay. |
| `hotfix/<short-slug>` | Correcciones urgentes y acotadas. |

## Rules

1. **Cursor** trabaja sobre archivos locales del repo y **no debe ejecutar operaciones de git**.
2. Los cambios funcionales deben hacerse en `feature/*` o en una rama específica según el tipo de tarea.
3. Los cambios pequeños de documentación pueden ir directo a `main` **solo si Camilo los revisa primero en VS Code**.
4. **No force-push** a `main`.
5. Todo merge a `main` requiere revisión y aprobación de **Camilo**.
6. Una **revisión externa** (si Camilo la solicita) es orientativa; no sustituye la aprobación del PO.
7. Los commits deben ser claros, cortos y en imperativo:
   - `add QA checklist`
   - `update agent brief template`
   - `create naming conventions doc`
8. Antes de merge, la tarea debe:
   - cumplir el brief, o
   - dejar explícito qué quedó recortado, bloqueado o pendiente.

## Working model

### Default model
Usar `main` + ramas cortas (`feature/*`, `docs/*`, `research/*`, `hotfix/*`).

### When to use `develop`
Usar `develop` solo si:
- hay varias tareas paralelas activas,
- hay riesgo de conflictos frecuentes,
- o el volumen del proyecto ya justifica una rama de integración.

## Workflow summary

Camilo prioriza → se crea brief con ID en `templates/task_brief.md` → se trabaja en rama dedicada si aplica → Cursor implementa cambios locales → Camilo revisa en VS Code → commit / push / merge a `main`.