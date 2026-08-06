# Reglas del Backend & APIs REST

## 1. Arquitectura en Capas
- **Estructura:** Separación clara entre Controladores (HTTP), Servicios (Lógica de Negocio), Repositorios/Entidades (Persistencia) y DTOs (Data Transfer Objects).
- **DTOs Obligatorios:** Ningún endpoint debe recibir o retornar entidades directamente. Siempre usar DTOs de entrada (*CreateDto*, *UpdateDto*) y DTOs de salida (*ResponseDto*).
- **Validación de Entradas:** Aplicar decoradores de validación automática en los DTOs (ej. `class-validator` en NestJS, annotations en Spring Boot/Java).

## 2. Estándares REST & Códigos de Estado
- **GET /resource:** Lista de recursos (Status 200 OK).
- **GET /resource/:id:** Recurso único (Status 200 OK, 404 Not Found si no existe).
- **POST /resource:** Crear recurso (Status 201 Created).
- **PUT/PATCH /resource/:id:** Actualizar recurso (Status 200 OK).
- **DELETE /resource/:id:** Eliminar recurso (Status 200 OK o 204 No Content).

## 3. Manejo de Errores & Respuestas Uniformes
- Retornar siempre respuestas estructuradas en formato JSON:
  ```json
  {
    "statusCode": 400,
    "message": "Mensaje descriptivo del error",
    "timestamp": "2026-08-05T23:00:00Z"
  }
  ```
