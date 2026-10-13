# DevSandbox-calidad-de-datos

> Diagnóstico y limpieza de un extracto bancario con más de diez tipos de defecto, con cada decisión documentada.

**Estado:** 🚧 sin empezar · **Categoría:** DevSandbox · **Tipo:** ETL (limpieza) · **Módulo del programa:** 05/02 · Limpieza y eficiencia

## Qué significa el nombre

El prefijo del repositorio indica el tamaño del proyecto:

| Prefijo | Tamaño | Qué es |
|---|---|---|
| **`DevSandbox-`** ← este | Hasta 8 h | Un proyecto pequeño para practicar un tema concreto: un espacio para probar, equivocarse y terminar rápido |
| `NightBuilds-` | 8 h o más | Un proyecto grande, con varias piezas (base de datos, orquestación, nube o API) y decisiones de diseño propias |

Este es un **DevSandbox**: el reto está estimado en 6–8 h.

## La problemática

Llega un extracto de un sistema antiguo con 1,560 transacciones y nadie se fía de él. Antes de usarlo hay que averiguar qué tiene mal, limpiarlo sin perder nada y dejar por escrito cada decisión para poder defenderla ante negocio.

## Los datos

| Dónde | Qué es |
|---|---|
| `datos/transacciones_sucias.csv` | 1,560 transacciones con defectos, enero a septiembre de 2026 |
| `datos/banco.sql` | Script de PostgreSQL con las tablas `clientes` y `cuentas` (base `banco_python`) |

Los archivos de `datos/` son **sintéticos**, generados para practicar: no corresponden a personas ni a operaciones reales.

## Qué hay que construir

El enunciado completo, con sus hitos y cómo comprobar cada uno, está en [`RETO.md`](RETO.md). No trae solución: el diseño es tuyo.

- [`docs/REGLAS.md`](docs/REGLAS.md): cómo se trabaja un DevSandbox y qué debe tener este README al terminar.
- [`docs/RUBRICA.md`](docs/RUBRICA.md): con qué criterios se evalúa.

## Cómo se ejecuta

*Pendiente: se escribe al cerrar el primer hito. Los comandos exactos, desde `git clone`.*

## Decisiones

*Pendiente: tres decisiones técnicas y la alternativa que se descartó en cada una.*

## Qué aprendí

*Pendiente.*

---

Reto del programa de Python e ingeniería de datos: [UNIR_Python_Certification](https://github.com/KevinMondragonDev/UNIR_Python_Certification).
