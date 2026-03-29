# Sistema de agentes

## Orquestador

**Responsabilidades**

- Traducir objetivos en work packages  
- Delegar a subagentes y consolidar entregables  
- Verificar dependencias y estado del proyecto  
- Disparar validaciones  
- Escalar decisiones cuando haya bloqueo  

**Artefactos sugeridos** (`/agents/orchestrator/`)

- Plantillas de brief de tarea  
- Formato de output consolidado  
- Registro de estado por sprint (o enlace a `docs/roadmap/`)  

---

## Subagentes

### A — Gameplay & Systems (`/agents/gameplay/`)

Gameplay loop, armas, input, daño, bots simples, scaffolding Blueprint/C++, integración entre sistemas.

### B — World & Design (`/agents/world/`)

Greyboxing, layout, encounters básicos, pacing, navegación, documentación de nivel.

### C — Art / 3D / Rigging (`/agents/art_rigging/`)

Pipeline de assets, formatos, naming, LODs, rig, animaciones placeholder, límites genérico vs manual.

### D — QA & Validation (`/agents/qa/`)

Test plans, smoke, regresión, performance checks, taxonomía de bugs, validación de prompts/outputs, criterios de aceptación.

### E — Market Research & Product Intelligence (`/agents/market/`)

Géneros, señales de mercado, benchmarks, monetización (insight), feedback público → diseño y GTM.

### F — Live Services & Operations (`/agents/liveops/`)

Telemetría conceptual, eventos, economy hooks futuros, retención, patch notes, release checklist.

---

## Capas de trabajo

1. **Orquestación** — Backlog, sprints, prioridad, criterios de aceptación, decisiones, estado por agente  
2. **Ejecución** — Cursor en repo, planes/artefactos de agentes, scripts locales, Unreal  
3. **Validación** — Automatización, revisión humana, smoke en engine, performance, documentación  
4. **Aprendizaje** — Errores recurrentes, prompts útiles, skills, templates, restricciones, deuda técnica  

---

## Convenciones (borrador)

- Cada tarea entra con **brief** claro: objetivo, alcance, fuera de alcance, dependencias, criterios de aceptación.  
- Cada agente documenta **output** en formato acordado (markdown en `/agents/<rol>/` o `/docs/` según tipo).  
- Decisiones que afectan al producto o al repo van a `TECH_DECISIONS_LOG.md` o `docs/decisions/`.  

Ajustar en `SPRINT_01_BACKLOG.md` y en la primera revisión de proceso.
