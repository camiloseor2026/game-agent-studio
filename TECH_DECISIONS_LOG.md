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

## Pendiente — Motor y versión

- **Decisión:** (pendiente) Unreal Engine versión X.X + plataformas objetivo.  
- Registrar aquí al instalar el proyecto.
