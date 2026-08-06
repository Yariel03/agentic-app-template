# Protocolo de Auto-Reparación (Self-Healing Loop)

## 1. Activación del Protocolo
Si durante la fase de desarrollo (Developer Agent) o compilación (QA Agent) ocurre un fallo en los comandos de prueba (`pnpm test`, `ng build`, etc.):

1. **PROHIBIDO:** No notificar inmediatamente al usuario ni rendirse al primer fallo.
2. **Inspección de Logs:** Extraer y leer la traza completa de error en la consola.
3. **Diagnóstico:** Identificar el tipo de error (error de tipos TypeScript, falta de importación, sintaxis, o test no cumplido).

## 2. Ciclo de Reintentos (Máximo 3 Intentos)
- **Intento 1:** Corregir las importaciones faltantes, firmas de métodos o tipos de datos. Reejecutar build/tests.
- **Intento 2:** Ajustar la lógica del componente o servicio manteniendo la compatibilidad con PrimeNG / Backend. Reejecutar build/tests.
- **Intento 3:** Si tras el 3er intento el error persiste, redactar una síntesis clara del problema técnico y solicitar orientación al usuario en el chat.
