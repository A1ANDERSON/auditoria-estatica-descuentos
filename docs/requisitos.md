# Auditoría de requisitos — propuestas sujetas a confirmación

Ppropuestas verificables, **no reglas de negocio aprobadas**. No implementar supuestos hasta confirmación del responsable.

| ID | Problema original | Propuesta verificable | Pendiente de confirmar |
|---|---|---|---|
| RF-01 | R-01 «rápidamente» no define medida ni carga | Para un precio, porcentaje y estado VIP válidos, el cálculo devolverá un resultado en ≤ 100 ms en el entorno de referencia acordado. | Umbral, entorno y volumen de operaciones. |
| RF-02 | R-02 «clientes importantes» y «especial» son ambiguos | Cuando `esVip` sea `true`, el sistema aplicará al descuento porcentual un beneficio VIP de valor definido en la tabla comercial aprobada. | Elegibilidad VIP; beneficio fijo o porcentual, monto y orden de aplicación. |
| RF-03 | R-03 admite excepciones de promoción sin definirlas | En operaciones sin promoción autorizada, el descuento total estará entre 0 y el precio; cualquier excepción requerirá identificador y regla de promoción aprobada. | Qué promociones permiten exceder el precio; límites, representación y comportamiento del total. |
| RF-04 | R-04 «correcto» no define resultado ni errores | Para entradas válidas, la función devolverá el precio final calculado conforme a RF-02 y RF-03; para entradas inválidas seguirá una política de error documentada. | Redondeo, moneda, tipos válidos, tratamiento de valores negativos, formato de salida y política de errores. |

## Criterios de aceptación propuestos
- RF-01: medición en entorno y carga acordados cumple el umbral aprobado.
- RF-02: los casos VIP y no VIP coinciden con ejemplos comerciales aprobados.
- RF-03: ninguna operación ordinaria genera descuento mayor que el precio; promociones siguen reglas explícitas.
- RF-04: entradas válidas y errores siguen ejemplos aprobados, con precisión y redondeo definidos.

## Matriz de trazabilidad
| ID | Artefacto | Evidencia prevista | Estado |
|---|---|---|---|
| RF-01 | `src/descuentos.js` | Caso de rendimiento futuro | Propuesto; sin validar |
| RF-02 | `src/descuentos.js` | Casos VIP/no VIP futuros | Regla comercial pendiente |
| RF-03 | `src/descuentos.js` | Casos límite/promoción futuros | Excepciones pendientes |
| RF-04 | `src/descuentos.js` | Casos de entrada/salida futuros | Política de errores pendiente |
