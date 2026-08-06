# Reglas de Base de Datos, Migraciones y Seeders

## 1. Diseño de Tablas & Relaciones
- Nombres de tablas en plural y minúsculas (ej. `docentes`, `evaluaciones`, `usuarios`).
- Toda tabla debe contar con:
  - `id`: Clave primaria (UUID o BigInt Autoincremental).
  - `created_at`: Timestamp de creación.
  - `updated_at`: Timestamp de última actualización.
  - `deleted_at`: Timestamp opcional para Soft Delete (Borrado Lógico).

## 2. Migraciones SQL Versionadas
- Ningún cambio de base de datos se realiza de forma directa o manual.
- Todo cambio se registra en un script de migración SQL numerado y fechado (ej. `V1__init_schema.sql`, `V2__add_status_to_evaluaciones.sql`).

## 3. Datos Semilla (Seeders) Obligatorios
- Para cada nueva funcionalidad que incluya tablas, se debe generar un script de **Seeders (Datos Ficticios)**.
- El script debe insertar al menos **10 registros realistas** para permitir pruebas visuales inmediatas en PrimeNG.
