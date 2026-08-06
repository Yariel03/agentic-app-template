---
name: git-commit-manager
description: Skill dedicada para analizar los cambios de código (`git status` / `git diff`), clasificar el tipo de commit, seleccionar el emoji correspondiente y realizar el commit formateado. Activar siempre que se finalice un cambio o funcionalidad.
---

# Skill: Git Commit Manager (Conventional Commits + Gitmoji)

## 1. Misión
Inspeccionar automáticamente los cambios en el espacio de trabajo, determinar la categoría del cambio (`feat`, `fix`, `refactor`, `docs`, etc.), identificar el ámbito afectado, seleccionar el emoji oficial correspondiente y ejecutar `git add .` seguido del `git commit` formateado.

## 2. Flujo de Ejecución

1. **Inspección de Cambios:**
   - Ejecutar `git status` y `git diff` (o `git diff --cached`).
2. **Análisis y Clasificación:**
   - Si se añadieron nuevas funciones -> `feat`
   - Si se arregló un bug -> `fix`
   - Si se refactorizó sin cambiar comportamiento -> `refactor`
   - Si es documentación -> `docs`
   - Si son pruebas -> `test`
   - Si actualiza dependencias/build -> `chore` o `build`
   - Si rompe compatibilidad -> añadir `!` o `BREAKING CHANGE!`
3. **Construcción del Mensaje:**
   - Formato: `:emoji: tipo(ámbito): asunto`
   - Seleccionar el emoji de la tabla de [`.gemini/rules/git-worktrees-commits.md`](file:///home/yariel/Documentos/2026/agentic-app-template/.gemini/rules/git-worktrees-commits.md).
4. **Ejecución del Commit:**
   ```bash
   git add .
   git commit -m ":emoji: tipo(ámbito): asunto"
   ```

## 💡 Ejemplos de Salida
- `:sparkles: feat(auth): implementar inicio de sesión con Google`
- `:bug: fix(ui): corregir desbordamiento en p-table`
- `:white_check_mark: test(api): agregar pruebas unitarias de evaluaciones`
- `:hammer: refactor(evaluaciones): optimizar uso de signals`
- `:books: docs(readme): actualizar guía de adopción`
