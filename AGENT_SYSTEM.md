# Sistema de agentes

## Roles en el repositorio

- **Camilo:** product owner, priorización y aprobación final.  
- **Cursor:** ejecución local sobre el repositorio (archivos, scripts, según brief); no es un rol de flujo interno, es la herramienta de implementación.  
- **Orquestador y subagentes:** roles de **flujo de trabajo** (cómo se parte el trabajo y qué se documenta en `agents/` y `docs/`); no son agentes en runtime dentro del repo.

## Orquestador

**Responsabilidades**

- Traducir objetivos en work packages  
- Delegar a subagentes y consolidar entregables  
- Verificar dependencias y estado del proyecto  
- Disparar validaciones  
- Escalar decisiones cuando haya bloqueo  

**Artefactos sugeridos** (`agents/orchestrator/`)

- Definición del subagente Cursor: `agents/orchestrator/orchestrator.md` (enlazada en `.cursor/agents/`)  
- Plantillas de brief de tarea; formato de output consolidado  
- Registro de estado por sprint (o enlace a `docs/roadmap/`)  

---

## Subagentes

### A — Gameplay & Systems (`agents/gameplay/`)

Gameplay loop, armas, input, daño, bots simples, scaffolding Blueprint/C++, integración entre sistemas. Subagente Cursor: `agents/gameplay/gameplay.md` (enlazado en `.cursor/agents/gameplay.md`). Skills: `skills/gameplay-system-breakdown/`, `mechanic-spec-writing/`, `feature-to-task-conversion/`, `unreal-gameplay-task-framing/`.

### B — World & Design (`agents/world/`)

Greyboxing, layout, encounters básicos, pacing, navegación, documentación de nivel. Subagente Cursor: `agents/world/world.md` (enlazado en `.cursor/agents/world.md`). Skills: `skills/level-layout-brief/`, `greybox-planning/`, `encounter-flow-mapping/`, `traversal-logic-review/`, `spatial-checklist/`.

### C — Art / 3D / Rigging (`agents/art_rigging/`)

Pipeline de assets, formatos, naming, LODs, rig, animaciones placeholder, límites genérico vs manual. Subagente Cursor: `agents/art_rigging/art-rigging.md` (enlazado en `.cursor/agents/art-rigging.md`). Skills: `skills/asset-pipeline-checklist/`, `rigging-handoff-brief/`, `placeholder-asset-planning/`, `unreal-asset-naming-validation/`, `art-integration-notes/`.

### D — QA & Validation (`/agents/qa/`)

Test plans, smoke, regresión, performance checks, taxonomía de bugs, validación de prompts/outputs, criterios de aceptación.

### E — Market Research & Product Intelligence (`/agents/market/`)

Géneros, señales de mercado, benchmarks, monetización (insight), feedback público → diseño y GTM.

### F — Live Services & Operations (`/agents/liveops/`)

Telemetría conceptual, eventos, economy hooks futuros, retención, patch notes, release checklist.

---

## Capas de trabajo

1. **Orquestación** — Backlog, sprints, prioridad, criterios de aceptación, decisiones, estado por agente  
2. **Ejecución** — Cambios en repo vía Cursor según brief; planes y artefactos de orquestador/subagentes; scripts locales; Unreal  
3. **Validación** — Automatización, revisión humana, smoke en engine, performance, documentación  
4. **Aprendizaje** — Errores recurrentes, prompts útiles, skills, templates, restricciones, deuda técnica  

---

## Convenciones (borrador)

- Cada tarea entra con **brief** claro: objetivo, alcance, fuera de alcance, dependencias, criterios de aceptación.  
- Cada agente documenta **output** en formato acordado (markdown en `/agents/<rol>/` o `/docs/` según tipo).  
- Decisiones que afectan al producto o al repo van a `TECH_DECISIONS_LOG.md` o `docs/decisions/`.  

Ajustar en `SPRINT_01_BACKLOG.md` y en la primera revisión de proceso.
