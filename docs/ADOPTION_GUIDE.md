# Guía de Adopción para Proyectos Existentes

Si su Señoría ya cuenta con un proyecto iniciado (por ejemplo, con código previo en Angular, PrimeNG, NestJS, Spring, etc.), siga estos simples pasos para dotarlo de toda la inteligencia de agentes:

---

## ⚡ Pasos de Adopción (Menos de 1 minuto)

1. **Copie las carpetas maestras a la raíz de su proyecto existente:**
   ```bash
   cp -r /home/yariel/Documentos/2026/agentic-app-template/.gemini /ruta/a/su-proyecto/
   cp -r /home/yariel/Documentos/2026/agentic-app-template/docs /ruta/a/su-proyecto/
   cp /home/yariel/Documentos/2026/agentic-app-template/AGENTS.md /ruta/a/su-proyecto/
   ```

2. **Abra su proyecto existente en Antigravity.**

3. **Escriba en el chat:**
   > **"Escanear proyecto existente"**

---

## 🤖 ¿Qué hará el Agente 0 en un Proyecto Existente?

- **Ingeniería Inversa Automática:** Leerá los archivos `package.json`, esquemas de BD y estructura del código existente.
- **Detección de Stack y Versiones:** Identificará si usa Angular v16/v17/v18, qué versión de PrimeNG tiene configurada y el backend actual.
- **Rellenado de Contexto (`PROJECT_CONTEXT.md`):** Extraerá las entidades de negocio ya creadas y los módulos existentes.
- **Cero Rompimiento de Código (Coexistencia Segura):** El sistema respetará la arquitectura previa y aplicará las nuevas reglas y componentes de PrimeNG únicamente a las nuevas funcionalidades o refactorizaciones autorizadas.
