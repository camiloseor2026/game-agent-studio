# Registro de decisiones técnicas

Formato sugerido por entrada (añadir al final del archivo):

```text
## YYYY-MM-DD — Título corto
- **Contexto:** …
- **Decisión:** …
- **Alternativas consideradas:** …
- **Consecuencias:** …
```

---

## 2026-03-29 — Inicialización del repositorio

- **Contexto:** Arranque del estudio agentic; necesidad de trazabilidad desde el día 1.  
- **Decisión:** Estructura `game-agent-studio` según charter; documentos raíz `README`, `PROJECT_CHARTER`, `AGENT_SYSTEM`, `SPRINT_01_BACKLOG`, `TECH_DECISIONS_LOG`.  
- **Alternativas consideradas:** Monorepo más amplio vs carpeta dedicada; se eligió carpeta dedicada bajo el workspace del usuario.  
- **Consecuencias:** Unreal vive bajo `unreal/`; la versión exacta del engine se registrará cuando se cree el `.uproject`.  

---

## 2026-03-29 — Proyecto Unreal Arena01 (ubicación y plantilla)

- **Contexto:** P01; proyecto creado desde el launcher/editor.  
- **Decisión:**  
  - **Ruta en repo:** `unreal/Arena01/` — archivo `Arena01.uproject`.  
  - **Project Location (disco):** `/Users/camilo.severiche/Documents/Clase Codigo/game-agent-studio/unreal` (proyecto **Arena01** dentro de esa carpeta).  
  - **Plantilla:** Top Down.  
  - **Código:** solo **Blueprint** (sin C++).  
  - **Target platform:** Desktop.  
  - **Quality preset:** Scalable (ligero) o Maximum (mejor visual); elección local del equipo.  
- **Motor:** Unreal Engine **5.7** (`EngineAssociation` en `.uproject`).  
- **Consecuencias:** Briefs y tareas P01 referencian `unreal/Arena01/`; no asumir carpeta `Source/` para lógica de gameplay salvo que se añada C++ después.

---

## 2026-03-29 — P01 Arena-01: modelo de combate y cámara (lock-in de producto)

- **Contexto:** Brief `docs/prototype_01_game_brief.md` §1b.  
- **Decisión:** Top-down o cámara fija simple (elegir una en implementación); enemigo persigue y mata por contacto (1 hit); jugador usa proyectil simple; 1 hit mata enemigo; 1 hit/contacto mata jugador.  
- **Alternativas consideradas:** Enemigo a distancia — **excluido** para P01.  
- **Consecuencias:** Secuencia de trabajo en `docs/prototype_01_implementation_sequence.md`.  
