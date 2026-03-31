# Prototype 01 — Game brief

**Task ID:** TASK-004  
**Tipo:** micro-prototipo jugable (validación de flujo agentic + Cursor + UE)

---

## 1. Prototype name

**Arena-01** — one-room shooter micro-vertical.

---

## 1b. Design lock-in (P01 — acordado)

Decisiones **cerradas** para implementación; no abrir alternativas en briefs hijos sin nuevo TASK.

| Tema | Decisión |
|------|-----------|
| Proyecto UE | Ruta: **`unreal/Arena01/`** (`Arena01.uproject`). Project Location: **`…/game-agent-studio/unreal`**. Plantilla **Top Down**, **Blueprint**, Desktop, UE **5.7** (ver `TECH_DECISIONS_LOG.md`). |
| Cámara | Alineada a plantilla **Top Down**; si se simplifica a fija, documentar en P01-03 + log. |
| Enemigo | **Persigue al jugador**; daño por **contacto** (no dispara). |
| Jugador | **Proyectil simple** (un tipo). |
| Daño | **1 impacto** mata al enemigo; **1 impacto/contacto** mata al jugador (vida = 1 o equivalente). |

---

## 2. Purpose of the prototype

Validar que el **sistema de trabajo** (brief → Orquestador → subagentes → Cursor → QA) puede producir un **loop jugable mínimo** en Unreal sin inflar alcance. No demuestra ambición de producto final; demuestra **ejecución coordinada y medible**.

---

## 3. Core gameplay loop

1. Aparecer en una **sala única** (arena).  
2. **Moverse** (plano) y **disparar proyectil** hacia el enemigo.  
3. **Eliminar** al enemigo con **un impacto** de proyectil **o** ser eliminado por **contacto** con el enemigo (un toque = muerte del jugador).  
4. Si el jugador muere: **reinicio** al estado inicial (misma sala, enemigo respawn).  
5. (Opcional) **Contador de kills** en pantalla.

---

## 4. Player actions

- Movimiento en plano (WASD o equivalente) con **top-down o cámara fija simple** (una variante por build P01).  
- **Un** disparo: **proyectil simple** (no hitscan salvo que el proyectil sea visualmente trivial y se documente como tal).  
- Sin inventario, sin sprint obligatorio, sin habilidades extra.

---

## 5. Enemy behavior

- **Un** tipo de enemigo.  
- **Persigue** al jugador (movimiento hacia el jugador; velocidad constante aceptable).  
- **Daño por contacto** al tocar al jugador (**1 hit** = muerte del jugador).  
- **Un proyectil** del jugador lo elimina (**1 hit**).  
- Sin disparo enemigo, sin oleadas, sin IA compleja: NavMesh opcional; si no, movimiento directo en el plano de juego.

---

## 6. Win / lose conditions

| Estado | Condición |
|--------|-----------|
| **Victoria de ronda** (opcional para P01) | Enemigo eliminado → respawn enemigo + sumar kill (si hay contador). |
| **Derrota** | **Contacto** con el enemigo (un hit; vida efectiva = 1). |
| **Reinicio** | Tras derrota (y opcionalmente tras victoria de ronda): recargar posiciones/vida en **la misma** arena sin menú complejo (ej. tecla R o auto-respawn tras 2 s). |

No se exige menú principal ni pantalla de créditos.

---

## 7. Minimum feature scope

- **Un** mapa / nivel: una habitación acotada (greybox UE: BSP o cubos).  
- **Un** personaje jugador con colisión y movimiento.  
- **Un** arma o componente de disparo con daño aplicable al enemigo.  
- **Un** enemigo con salud = 1 “unidad” de daño del jugador.  
- **HUD mínimo**: vida (o indicador binario vivo/muerto) + opcional contador de kills.  
- **Game Mode** o lógica equivalente que gestione reinicio.  
- Contenido **placeholder** (materiales/cubos); sin pipeline de arte final.

---

## 8. Out of scope

- Multiplayer, netcode, servicios en vivo, telemetría implementada.  
- Física avanzada, destrucción, cover system, IA con árboles complejos, más de un tipo de enemigo, **enemigo a distancia / proyectiles enemigos**.  
- Mundo grande, múltiples salas, narrativa, audio final, cinemáticas.  
- Economía, progresión meta, guardado persistente más allá de lo necesario para PIE.  
- Optimización de producción (LOD fino, light bake complejo).

---

## 9. What this prototype validates (agent workflow)

| Área | Qué se prueba |
|------|----------------|
| **Orquestador** | Orden de TASKs (ej. convenciones → proyecto UE → greybox → pawn → daño → enemigo → HUD → reinicio → QA smoke). |
| **Gameplay** | Specs mínimas y conversión a briefs ejecutables para Cursor. |
| **World** | Brief de layout de una sola arena + greybox sin creep. |
| **Art/Rigging** | Placeholders y naming; sin arte final. |
| **QA** | Smoke checklist + `acceptance-check` / criterios del brief; `tdd-process` opcional (casos antes de código en el siguiente ciclo). |
| **Market / LiveOps** | **No** son bloqueantes para P01; pueden correr en paralelo solo como docs si Camilo lo pide. |
| **Transversal** | `task-brief-reader`, `scope-guard`, `repo-safe-editing`, `structured-handoff`, `unreal-task-framing` en cada paso. |

---

## 10. Suggested next implementation tasks (post-brief)

Orden sugerido (ajustar IDs en backlog real):

1. **TASK-P01-01** — Registrar versión UE y confirmar ruta del `.uproject` (`TECH_DECISIONS_LOG.md` + `unreal/`).  
2. **TASK-P01-02** — Greybox arena única (`World` + Cursor): dimensiones mínimas, spawn jugador/enemigo marcados.  
3. **TASK-P01-03** — Pawn jugador: movimiento + cámara (`Gameplay` + Cursor).  
4. **TASK-P01-04** — Disparo + daño 1-hit al enemigo (`Gameplay` + Cursor).  
5. **TASK-P01-05** — Enemigo: un comportamiento simple + muerte (`Gameplay` + Cursor).  
6. **TASK-P01-06** — Vida jugador + muerte + reinicio (`Gameplay` + Cursor).  
7. **TASK-P01-07** — HUD mínimo + kill counter opcional (`Gameplay` o UI mínima + Cursor).  
8. **TASK-P01-08** — Smoke checklist específico P01 (`QA` → `docs/qa/` o output de agente).  
9. **TASK-P01-09** — `acceptance-check` formal contra este brief + ajuste de criterios si hay GAPs documentados.

Cada TASK debe usar `templates/task_brief.md` con **Fuera de alcance** explícito y referencia a este documento.

---

## Acceptance criteria (brief-level)

- [ ] Un jugador puede completar al menos un ciclo: entrar → disparar → matar enemigo → (opcional) ver contador → morir o reiniciar y repetir.  
- [ ] Todo ocurre en **una** arena sin cargar otros niveles.  
- [ ] Ningún ítem de la sección **Out of scope** aparece como requisito en los briefs hijos sin decisión de Camilo.  
- [ ] Existe documento de smoke P01 que referencie este brief.
