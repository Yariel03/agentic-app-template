# Protocolo de Git Worktrees & Convención de Commits con Emojis

## 1. Flujo de Git Worktrees (Aislamiento de Funcionalidades)
- Para cada nueva historia o funcionalidad (`feature/US-XXX`), el agente creará o trabajará en un **Git Worktree** independiente para no ensuciar la rama principal.
- Comando para crear worktree:
  ```bash
  git worktree add -b feature/US-XXX ../worktree-US-XXX
  ```
- Una vez finalizada y aprobada la funcionalidad, se realiza el merge a la rama principal y se elimina el worktree:
  ```bash
  git worktree remove ../worktree-US-XXX
  ```

---

## 2. Convención de Commits (Conventional Commits + Gitmoji)

### Estructura del Mensaje de Commit:
```text
:emoji: tipo(ámbito): asunto
```

### Componentes:
1. **emoji:** Emoji de la tabla oficial según la categoría del cambio.
2. **tipo:** Obligatorio. Categoria del cambio:
   - `feat`: Añadir nueva función.
   - `fix`: Arreglar un bug.
   - `refactor`: Mejorar código existente sin cambiar comportamiento.
   - `docs`: Cambios en documentación.
   - `chore` o `build`: Actualización de dependencias o build.
   - `test`: Agregar o corregir pruebas.
   - `!` o `BREAKING CHANGE!`: Cambio que rompe compatibilidad anterior.
3. **ámbito (scope):** Opcional. Sustantivo de la sección afectada (ej: `api`, `auth`, `ui`, `login`, `evaluaciones`).
4. **asunto (subject):** Descripción corta en imperativo.

---

## 🎨 Tabla Oficial de Emojis para Commits

| Commit type | Emoji |
|:---|:---|
| Initial commit | :tada: `:tada:` |
| Version tag | :bookmark: `:bookmark:` |
| New feature | :sparkles: `:sparkles:` |
| Bugfix | :bug: `:bug:` |
| Metadata | :card_index: `:card_index:` |
| Documentation | :books: `:books:` |
| Documenting source code | :bulb: `:bulb:` |
| Performance | :racehorse: `:racehorse:` |
| Cosmetic | :lipstick: `:lipstick:` |
| Tests | :rotating_light: `:rotating_light:` |
| Adding a test | :white_check_mark: `:white_check_mark:` |
| Make a test pass | :heavy_check_mark: `:heavy_check_mark:` |
| General update | :zap: `:zap:` |
| Improve format/structure | :art: `:art:` |
| Refactor code | :hammer: `:hammer:` |
| Removing code/files | :fire: `:fire:` |
| Continuous Integration | :green_heart: `:green_heart:` |
| Security | :lock: `:lock:` |
| Upgrading dependencies | :arrow_up: `:arrow_up:` |
| Downgrading dependencies | :arrow_down: `:arrow_down:` |
| Lint | :shirt: `:shirt:` |
| Translation | :alien: `:alien:` |
| Text | :pencil: `:pencil:` |
| Critical hotfix | :ambulance: `:ambulance:` |
| Deploying stuff | :rocket: `:rocket:` |
| Fixing on MacOS | :apple: `:apple:` |
| Fixing on Linux | :penguin: `:penguin:` |
| Fixing on Windows | :checkered_flag: `:checkered_flag:` |
| Work in progress | :construction: `:construction:` |
| Adding CI build system | :construction_worker: `:construction_worker:` |
| Analytics or tracking code | :chart_with_upwards_trend: `:chart_with_upwards_trend:` |
| Removing a dependency | :heavy_minus_sign: `:heavy_minus_sign:` |
| Adding a dependency | :heavy_plus_sign: `:heavy_plus_sign:` |
| Docker | :whale: `:whale:` |
| Configuration files | :wrench: `:wrench:` |
| Package.json in JS | :package: `:package:` |
| Merging branches | :twisted_rightwards_arrows: `:twisted_rightwards_arrows:` |
| Bad code / need improv. | :hankey: `:hankey:` |
| Reverting changes | :rewind: `:rewind:` |
| Breaking changes | :boom: `:boom:` |
| Code review changes | :ok_hand: `:ok_hand:` |
| Accessibility | :wheelchair: `:wheelchair:` |
| Move/rename repository | :truck: `:truck:` |

---

## 💡 Ejemplos de Commits Válidos
- `:sparkles: feat(auth): implementar inicio de sesión con Google`
- `:bug: fix(ui): corregir desbordamiento en p-table`
- `:white_check_mark: test(api): agregar pruebas unitarias de login`
- `:hammer: refactor(evaluaciones): optimizar uso de signals`
- `:books: docs(readme): actualizar guía de adopción`
