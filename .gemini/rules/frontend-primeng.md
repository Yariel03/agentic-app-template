# Reglas del Frontend - Angular + PrimeNG

## 1. Arquitectura de Componentes (Angular 17+)
- **Standalone Components:** Todos los componentes deben ser `standalone: true`. No usar NgModules.
- **Inyección de Dependencias:** Usar la función `inject()` de `@angular/core` en lugar de constructores clásicos.
- **Change Detection:** Usar `changeDetection: ChangeDetectionStrategy.OnPush` en todos los componentes para máximo rendimiento.
- **Reactividad:** Utilizar `signal()`, `computed()` y `effect()` para la gestión del estado reactivo local. Evitar suscripciones manuales con RxJS siempre que sea posible (usar `toSignal` o `async` pipe).

## 2. Sistema de Diseño & PrimeNG
- **Componentes Nativos:** Usar exclusivamente la suite de componentes PrimeNG (`p-table`, `p-dialog`, `p-button`, `p-dropdown`, `p-toast`, `p-blockUI`, `p-rating`, etc.).
- **Variantes de Botones:**
  - Acción Primaria: `<p-button label="..." icon="pi pi-check" severity="primary"></p-button>`
  - Acción Secundaria / Cancelar: `<p-button label="Cancelar" icon="pi pi-times" severity="secondary" [outlined]="true"></p-button>`
  - Acción Peligrosa / Borrar: `<p-button severity="danger"></p-button>`
- **Iconografía:** Usar exclusivamente PrimeIcons (`pi pi-*`).
- **Layout y Espaciados:** Utilizar clases utilitarias de PrimeFlex / PrimeNG CSS (`flex`, `align-items-center`, `gap-3`, `mb-4`, `p-fluid`).
- **Variables de Tema:** No utilizar colores en hexadecimal en estilos locales. Usar siempre variables CSS del tema de PrimeNG (ej. `var(--primary-color)`, `var(--surface-border)`, `var(--text-color)`).

## 3. Manejo de Formularios
- Usar **ReactiveForms** (`FormBuilder`, `FormGroup`, `FormControl`).
- Mostrar mensajes de error de validación estandarizados con `<p-message severity="error">` o `<small class="p-error">`.
