---
name: repo-safe-editing
description: Constrains repository edits to paths and files named in the task brief, avoids unrelated changes, and respects no-git and no-delete-folder rules when stated. Use whenever Cursor or an agent proposes file changes in this repo.
---

# Repo-safe editing

## Reglas (por defecto del estudio)

1. **Solo** archivos y carpetas **mencionados en el brief** o estrictamente necesarios para cumplir un criterio explícito; el resto es **fuera de alcance**.
2. **No** operaciones `git` salvo que el brief lo autorice.
3. **No** borrar carpetas salvo instrucción explícita.
4. **No** “refactors de limpieza” en archivos no relacionados con la tarea.
5. Cambios **mínimos**: preferir el diff más pequeño que cumpla los criterios.

## Antes de editar

- [ ] ¿Cada archivo tocado está justificado por el brief o por una dependencia directa?
- [ ] ¿Las restricciones del brief se respetan?
- [ ] Si falta una ruta, ¿pedir aclaración o brief ampliado en lugar de adivinar?

## Si el brief es ambiguo

Parar y proponer **una** pregunta concreta o sugerir actualizar el brief; no expandir archivos por asunción.
