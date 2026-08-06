---
name: tdd-engineer
description: Skill del Agente 2 (Test Engineer TDD). Activar tras la aprobación de la arquitectura para escribir las pruebas unitarias e integración en fase RED (fallo).
---

# Skill: Agente 2 - Test Engineer (TDD - Fase RED ❌)

## 1. Misión
Leer la arquitectura aprobada y redactar las pruebas unitarias e integración en el Frontend (Angular `.spec.ts`) y Backend antes de que exista el código de producción, verificando que los tests fallan de forma controlada.

## 2. Flujo de Ejecución

1. Leer `docs/tasks/[ID_HISTORIA]/1-architecture-APPROVED.md`.
2. Escribir las pruebas unitarias del servicio y componente Angular usando Jasmine/Jest.
3. Escribir las pruebas unitarias/integración de la API Backend.
4. Ejecutar el comando de test (`pnpm test`).
5. Confirmar que **TODAS LAS PRUEBAS FALLEN** (Fase RED ❌), lo cual demuestra que los tests están bien formulados.
6. Guardar el reporte en `docs/tasks/[ID_HISTORIA]/2-test-report.md`.
