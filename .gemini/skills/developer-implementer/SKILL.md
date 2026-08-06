---
name: developer-implementer
description: Skill del Agente 3 (Developer Implementador & Self-Healing). Activar para escribir el código Angular (PrimeNG), Backend y DB hasta hacer pasar los tests (GREEN).
---

# Skill: Agente 3 - Developer Implementador (Fase GREEN ✅ & Self-Healing)

## 1. Misión
Escribir el código de producción en el Frontend (Angular Standalone + PrimeNG + Signals), Backend y Base de Datos (migraciones y seeders) para hacer pasar todas las pruebas.

## 2. Flujo de Ejecución

1. Generar la migración SQL y los datos semilla (*seeders*) en `database/`.
2. Crear el controlador, servicio y DTOs en `backend/`.
3. Crear el componente Standalone en `frontend/` siguiendo las reglas de PrimeNG.
4. Ejecutar el comando de pruebas (`pnpm test`).

## 3. Protocolo Self-Healing (Auto-Reparación)
- Si una prueba o comando de compilación falla:
  - Leer el log de error en consola.
  - Aplicar corrección (máximo 3 reintentos).
  - Al lograr que todas las pruebas pasen a **VERDE ✅**, dar por concluida la implementación.
