# AGENTS.md - Sistema Maestro de Orquestación de Agentes

Bienvenido al Repositorio Plantilla Agnóstico. Este archivo define el flujo de trabajo, las reglas inquebrantables y la secuencia de orquestación de subagentes para cualquier proyecto de software desarrollado en este entorno.

---

## 🏛️ Principios Universales e Inquebrantables

1. **Agnóstico al Proyecto:** Este ecosistema se adapta a cualquier dominio (CRM, ERP, EduTech, E-commerce, etc.) y a cualquier stack tecnológico definido en la Fase de Inicio.
2. **Control del Amo y Señor (Human-in-the-Loop):** EL ORQUESTADOR TIENE ESTRICTAMENTE PROHIBIDO iniciar las fases de código/TDD sin la confirmación explícita del usuario ("Aprobado", "Proceder") sobre la propuesta de arquitectura y prototipo visual.
3. **Paso de Testigo por Artefactos:** Cada subagente produce un entregable en disco (`docs/tasks/`) que sirve como señal de arranque para la siguiente etapa.
4. **Protección de la Ventana de Contexto:** El trabajo pesado de desarrollo y pruebas se ejecuta en subagentes aislados (`invoke_subagent`). Solo los resúmenes ejecutivos se reportan al hilo principal.

---

## 🔄 El Pipeline de Trabajo (Etapas Secuenciales)

```
 ┌────────────────────────────────────────────────────────┐
 │           FASE 0. PRODUCT OWNER / DISCOVERY            │
 └───────────────────────────┬────────────────────────────┘
                             │ (Crea PROJECT_CONTEXT.md y BACKLOG.md)
                             ▼
 ┌────────────────────────────────────────────────────────┐
 │           FASE 1. ARQUITECTO & UX DESIGNER             │
 └───────────────────────────┬────────────────────────────┘
                             │ (Genera 1-architecture-PROPOSAL.md + Mockup UI en Imagen)
                             ▼
 🛑 ────── [ PUNTO DE CONTROL Y REVISIÓN DEL AMO Y SEÑOR ] ──────
    └─► Debate, ajustes e imágenes de prototipo
    └─► Confirmación de aprobación del usuario
                             │
                             ▼
 ┌────────────────────────────────────────────────────────┐
 │           FASE 2. TEST ENGINEER (TDD - RED ❌)          │
 └───────────────────────────┬────────────────────────────┘
                             │ (Escribe pruebas unitarias/integración que fallan)
                             ▼
 ┌────────────────────────────────────────────────────────┐
 │           FASE 3. DEVELOPER (IMPLEMENTADOR - GREEN ✅)  │
 └───────────────────────────┬────────────────────────────┘
                             │ (Escribe código hasta que todos los tests pasen)
                             │ (🏥 Aplica Bucle Self-Healing si la compilación falla)
                             ▼
 ┌────────────────────────────────────────────────────────┐
 │           FASE 4. QA, SEGURIDAD & COMMIT (GITMOJI)     │
 └────────────────────────────────────────────────────────┘
                             │ (Audita roles, valida linter/build, realiza commit con emojis y elimina worktree)

```

---

## 📁 Estructura del Espacio de Trabajo

- `.gemini/agents.json`: **Registro y Mapeo Oficial de Subagentes, Triggers, Skills y Herramientas.**
- `.gemini/rules/`: Directrices técnicas (Angular/PrimeNG, Backend, DB, Self-Healing).
- `.gemini/skills/`: Recetas de ejecución para subagentes (`SKILL.md`).

- `docs/PROJECT_CONTEXT.md`: Visión del negocio, dominio y entidades globales.
- `docs/STACK_SPECIFICATION.md`: Tecnologías elegidas (Frontend, Backend, DB, Theme).
- `docs/BACKLOG.md`: Lista ordenada de historias de usuario y funcionalidades.
- `docs/tasks/`: Entregables y artefactos por funcionalidad desarrollada.
- `database/`: Scripts de migración SQL y datos semilla (*seeders*).
- `backend/`: Código fuente del servicio de API Backend.
- `frontend/`: Código fuente de la aplicación Frontend (Angular + PrimeNG).

---

## 🛠️ Triggers de Inicio

### A. Para un Proyecto NUEVO (Desde Cero)
- Escribir en el chat **"Inicia el proyecto"** o usar la skill `/project-init`.
- El **Agente 0** realizará la entrevista guiada para definir la idea, el stack y los roles.

### B. Para un Proyecto EXISTENTE (Código ya creado)
- Copiar la carpeta `.gemini/`, `AGENTS.md` y `docs/` a la raíz del proyecto existente.
- Escribir en el chat **"Escanear proyecto existente"** (o `/project-scan`).
- El **Agente 0 (Reverse Engineering)** escaneará automáticamente:
  1. `package.json` / archivos de configuración para auto-detectar el Stack real.
  2. Estructura de carpetas y entidades de la Base de Datos/Backend existentes.
  3. Autogenerará `PROJECT_CONTEXT.md` y `STACK_SPECIFICATION.md` basándose en su código actual.
  4. Quedará listo para desarrollar nuevas historias respetando la arquitectura existente.

