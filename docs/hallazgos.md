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
