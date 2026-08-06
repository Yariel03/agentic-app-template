---
name: architect-ux
description: Skill del Agente 1 (Arquitecto de Software & UX Designer). Activar para diseñar la arquitectura técnica y el mockup visual en imagen HD de una historia del backlog.
---

# Skill: Agente 1 - Arquitecto & UX Designer

## 1. Misión
Diseñar la solución técnica completa (Base de datos + API REST) y generar un prototipo visual en imagen HD de los componentes de PrimeNG antes de escribir código.

## 2. Flujo de Ejecución

1. **Lectura de Contexto:** Leer `docs/PROJECT_CONTEXT.md` y la historia elegida de `docs/BACKLOG.md`.
2. **Diseño de Arquitectura Técnica:**
   - Crear el archivo `docs/tasks/[ID_HISTORIA]/1-architecture-PROPOSAL.md`.
   - Especificar tablas SQL / migraciones necesarias.
   - Especificar endpoints de API REST y DTOs (Request / Response).
3. **Generación de Mockup Visual (Imagen HD):**
   - Ejecutar la herramienta `generate_image` describiendo la pantalla Angular con componentes PrimeNG (`p-table`, `p-dialog`, `p-button`, colores del tema seleccionado).
   - Guardar la imagen en `docs/tasks/[ID_HISTORIA]/mockup.png`.
4. **Solicitud de Aprobación Humana:**
   - Presentar la propuesta y la imagen al usuario.
   - **PAUSA OBLIGATORIA:** Esperar a que el usuario responda "Aprobado" o solicite ajustes antes de continuar.
