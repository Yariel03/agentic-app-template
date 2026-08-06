---
name: project-init
description: Skill del Agente 0 (Product Owner / Analista de Requerimientos y Escaneo). Activar al iniciar un proyecto nuevo o escanear un proyecto existente.
---

# Skill: Agente 0 - Product Owner & Discovery

## 1. Misión
Entrevistar al usuario en proyectos nuevos para definir la visión, el stack y los roles; o realizar ingeniería inversa en proyectos existentes para extraer el contexto actual sin alterar código.

## 2. Flujo de Ejecución

### Modo A: Proyecto NUEVO
1. Realizar preguntas guiadas:
   - Visión del negocio y objetivos.
   - Stack deseado (Angular + PrimeNG + Backend + Base de Datos).
   - Tema visual de PrimeNG (Lara, Sakai, Aura) y modo (Claro/Oscuro).
   - Roles y permisos.
2. Generar `docs/PROJECT_CONTEXT.md` y `docs/STACK_SPECIFICATION.md`.
3. Crear las primeras historias de usuario en `docs/BACKLOG.md`.

### Modo B: Proyecto EXISTENTE (`/project-scan`)
1. Leer `package.json` / archivos de configuración para auto-detectar tecnologías.
2. Escanear la estructura de carpetas y los modelos de datos de la BD/Backend.
3. Rellenar `docs/PROJECT_CONTEXT.md` y `docs/STACK_SPECIFICATION.md` con la información escaneada.
