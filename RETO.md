# 🚀 Sideproject — Calidad de datos

**Repositorio:** `sideproject-calidad-de-datos` · **Tipo:** ETL (limpieza) · **Tiempo:** 6–8 h · **Después de:** lecciones 1 a 5 de esta sección

> Reglas, README y lista de cierre: [`SIDEPROJECTS.md`](docs/REGLAS.md). **No hay solución: el diseño es tuyo.**

## El caso

Llega un extracto de un sistema antiguo: `datos/transacciones_sucias.csv`, 1,560 transacciones de enero a septiembre de 2026. Nadie se fía de él. Antes de usarlo hay que saber qué tiene mal, limpiarlo y dejar constancia de cada decisión.

El script que generó estos datos no está en este repositorio a propósito: encontrar los defectos es el reto.

## Qué practicas

| Lección | Dónde aparece |
|---|---|
| Tipos, rangos y duplicados | El diagnóstico y las primeras reglas |
| Texto, categorías y nulos | Normalizar y validar entre columnas |
| Código eficiente / pandas eficiente | Medir y vectorizar una regla |
| Polars | Reescribir el pipeline en modo perezoso |

## Hitos

**Hito 1 — Diagnóstico.** Un script que encuentre y cuente los problemas, sin modificar nada. Hay al menos **10 tipos de defecto**.
*Comprueba:* tu lista tiene 10 o más, cada uno con su número de filas.

**Hito 2 — Decisiones por escrito.** `REPORTE.md` con una tabla: defecto · filas · decisión (corregir, descartar o marcar) · por qué.
*Comprueba:* cada decisión la podrías defender ante alguien de negocio.

**Hito 3 — Reglas.** `limpieza.py` con una función por regla (recibe y devuelve un DataFrame). Salida en Parquet con tipos correctos.
*Comprueba:* ninguna regla menciona un id concreto.

**Hito 4 — Nada se pierde.** Las filas descartadas van a `rechazadas.csv` con una columna `motivo`.
*Comprueba:* filas de entrada = limpias + rechazadas (o explicas la diferencia).

**Hito 5 — Garantías.** `assert` finales: ids únicos, montos > 0, sin fechas futuras, categorías válidas, `cuenta_id` existente en PostgreSQL.
*Comprueba:* ejecutarlo dos veces da exactamente el mismo resultado.

**Hito 6 — Medir.** Una regla escrita fila a fila y vectorizada, medidas con `timeit`. Después, el pipeline completo en Polars.
*Comprueba:* la versión de Polars produce el mismo Parquet.

## Preguntas para defenderlo

- Dos filas con el mismo id y distinto monto: ¿con cuál te quedaste y por qué?
- ¿Qué es peor: descartar una fila buena o cargar una mala?
- ¿Cambia el resultado si aplicas las reglas en otro orden?

## Súbelo de nivel

- Columna `monto_usd` con el tipo de cambio de tu sideproject de ingesta (resuelve los fines de semana).
- Reglas definidas como datos (YAML), no como código. Compáralo con `04_retos_de_python/reto_13`.
