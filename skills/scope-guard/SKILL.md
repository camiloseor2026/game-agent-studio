---
name: scope-guard
description: Detects scope creep during tasks: new features, charter conflicts, implied multiplayer or monetization, or parallel work not in the brief. Use when planning, mid-task, or before accepting expanded deliverables.
---

# Scope guard

## Señales de expansión (detener y etiquetar)

- Nuevos **features** o sistemas no listados en **Incluye** del brief.
- Pedidos tipo “ya de paso…” sin nuevo TASK ID.
- Conflicto con **`PROJECT_CHARTER.md`** (multiplayer, mundo abierto, monetización pesada, etc. en fase prohibida).
- **Dos dominios** a la vez (ej. gameplay + pipeline de arte completo) sin brief partido.
- Archivos o carpetas **fuera** de las rutas del brief sin justificación de dependencia directa.
- Criterios de aceptación **movidos** o añadidos sin Camilo/Orquestador.

## Acción

1. Nombrar la expansión en una frase.
2. Clasificar: **bloqueante** | **opcional** | **error de brief**.
3. Recomendación: **nuevo brief** | **escalación a Camilo** | **recortar**.
4. **No continuar** implementando la expansión hasta decisión explícita.

## Excepción

Corrección de **bugs que impiden** cumplir criterios ya escritos: documentar en handoff como alcance de corrección, no como feature nueva.
