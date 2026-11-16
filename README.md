# Auditoría estática de descuentos — Unidad 1

Proyecto académico de verificación y validación. Incluye código base original, requisitos propuestos, checklist y hallazgos preliminares.

## Reproducción
1. Instalar Node.js y abrir el proyecto en VS Code.
2. Ejecutar `npm install`.
3. Ejecutar `npm run lint > evidencias/lint-inicial.txt 2>&1` (en PowerShell, preferir `npm run lint *> evidencias/lint-inicial.txt`).
4. Registrar el resultado inicial y hacer inspección real con autor, revisor y registrador.
5. Confirmar reglas de negocio antes de modificar comportamiento.
6. Corregir infracciones de estilo confirmadas, ejecutar de nuevo ESLint y guardar `evidencias/lint-final.txt`.
7. Realizar al menos 4 commits significativos y una revisión por pull request con 2 comentarios técnicos reales o acta equivalente.

## Reglas ESLint
- `no-var`: prefiere declaraciones con ámbito de bloque.
- `eqeqeq`: evita coerción implícita de tipos.
- `no-unused-vars`: identifica declaraciones sin uso.
- `curly`: exige llaves para bloques de control.

## Estado
Las evidencias de ejecución, revisión por pares y GitHub están pendientes: no se incluyen salidas o revisiones inventadas.
