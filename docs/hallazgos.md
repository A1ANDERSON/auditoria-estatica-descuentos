# Hallazgos preliminares de lectura humana — NO es acta de revisión por pares

| ID | Origen | Severidad preliminar | Evidencia | Acción propuesta | Estado |
|---|---|---|---|---|---|
| H-01 | Humana | Alta | `porcentaje > 100` solo imprime mensaje y continúa calculando | Definir y aprobar política de entrada inválida | Abierto |
| H-02 | Humana | Alta | No se valida `precio` negativo, nulo, NaN o no numérico | Acordar dominio de entrada y validación | Abierto |
| H-03 | Humana | Alta | `descuento + 10` aplica importe VIP fijo sin especificación aprobada | Confirmar beneficio VIP y moneda | Abierto |
| H-04 | Humana | Alta | `precio - descuento` puede ser negativo | Definir límite y excepciones promocionales | Abierto |
| H-05 | Humana | Media | No hay política explícita de redondeo monetario | Aprobar precisión y redondeo | Abierto |
| H-06 | Humana | Media | No se maneja `porcentaje < 0` | Confirmar rango de porcentaje | Abierto |
| H-07 | ESLint (esperado; no ejecutado) | Baja | Uso de `var` | Aplicar `no-var` | Pendiente de ejecución |
| H-08 | ESLint (esperado; no ejecutado) | Baja | Uso de `==` | Aplicar `eqeqeq` | Pendiente de ejecución |
| H-09 | ESLint (esperado; no ejecutado) | Baja | `if` sin llaves | Aplicar `curly` | Pendiente de ejecución |

**Nota:** `no-unused-vars` es una regla preventiva; no se presupone que el código base tenga una infracción. Confirmar salidas reales de ESLint antes de completar el informe.


## Resultados del análisis estático

Se realizó una revisión estática del módulo
`src/descuentos.js`, combinando los resultados
de ESLint con una inspección manual del código.

| ID | Origen | Hallazgo | Severidad | Acción | Estado |
|---|---|---|---|---|---|
| H-01 | ESLint | Uso de `var` en líneas 2 y 5 del código inicial. | Baja | Sustituir por `let` y `const`. | Corregido |
| H-02 | ESLint | Uso de comparación `==` en línea 3. | Media | Sustituir por `===`. | Corregido |
| H-03 | ESLint | Instrucciones `if` sin llaves en líneas 3 y 4. | Baja | Incorporar llaves. | Corregido |
| H-04 | Revisión manual | El porcentaje mayor a 100 solo genera un mensaje y no detiene el cálculo. | Alta | Confirmar comportamiento esperado para valores inválidos. | Pendiente |
| H-05 | Revisión manual | El descuento VIP agrega 10 unidades sin una regla de negocio confirmada. | Alta | Consultar cómo debe calcularse el beneficio VIP. | Pendiente |
| H-06 | Revisión manual | El descuento podría superar el precio y producir un total negativo. | Alta | Confirmar restricciones y excepciones de promociones. | Pendiente |

### Conclusión preliminar

El análisis inicial de ESLint identificó cinco
infracciones de reglas de código, agrupadas
en tres categorías: `no-var`, `eqeqeq` y `curly`.

Después de realizar las correcciones,
el análisis final no reportó infracciones.

Sin embargo, la ausencia de alertas de ESLint
no garantiza que el módulo cumpla todas
las reglas de negocio.

Los hallazgos H-04, H-05 y H-06 permanecen
pendientes hasta confirmar los requisitos
con los responsables del sistema.
