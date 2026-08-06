---
name: qa-security-auditor
description: Skill del Agente 4 (QA, Security Auditor y Documentador). Activar tras el desarrollo para validar seguridad de roles, linter, compilación limpia y actualización de Swagger/Backlog.
---

# Skill: Agente 4 - QA, Seguridad & Documentación

## 1. Misión
Auditar la calidad del código, verificar permisos/roles por seguridad, comprobar que el build pase sin advertencias y actualizar la documentación del proyecto.

## 2. Flujo de Ejecución

1. **Auditoría de Seguridad:**
   - Verificar que los endpoints tengan guardias de autenticación JWT y roles.
   - Verificar que en Angular las rutas y componentes respeten la autorización.
2. **Control de Calidad (QA) & Estilos:**
   - Validar cumplimiento estricto del sistema de diseño PrimeNG.
   - Ejecutar el linter (`pnpm lint`) y el build completo (`pnpm build`).
3. **Commit Personalizado (Conventional Commits + Gitmoji):**
   - Trabajar la funcionalidad en un **Git Worktree** aislado (`git worktree add`).
   - Ejecutar `git add .` para incluir todos los cambios.
   - Generar el mensaje de commit siguiendo la plantilla `:emoji: tipo(ámbito): asunto` usando la tabla de [`.gemini/rules/git-worktrees-commits.md`](file:///home/yariel/Documentos/2026/agentic-app-template/.gemini/rules/git-worktrees-commits.md).
   - Ejemplo: `:sparkles: feat(auth): implementar inicio de sesión con Google`.
4. **Documentación & Cierre:**
   - Actualizar especificación Swagger/OpenAPI.
   - Marcar la historia como completada en `docs/BACKLOG.md`.

