# ¿Cambió la anchura del cráneo entre dos periodos?

Se midieron 60 cráneos, 30 del predinástico temprano y 30 del tardío, para ver si la
diferencia de anchura entre los dos grupos es real o fruto del azar. Es real: los del
periodo tardío son, de media, casi un milímetro más anchos. Pero ese milímetro es poco
al lado de lo que varían los cráneos dentro de cada grupo.

Ejercicio del módulo de Estadística del Máster en Big Data, Data Science e IA de la
Universidad Complutense (curso 2025-26).

| Grupo | Cráneos | Media (mm) | Desviación típica (mm) |
|---|---|---|---|
| Predinástico temprano | 30 | 131,53 | 0,82 |
| Predinástico tardío | 30 | 132,47 | 1,01 |

![Diagrama de caja y bigotes](images/caja_bigotes.svg)

## Cómo está hecho

Descriptivos y diagrama de caja por grupo, normalidad con Kolmogorov-Smirnov, igualdad
de varianzas con Levene, intervalos de confianza y, al final, la prueba t de Student
para muestras independientes. Da p = 0,0002, y el intervalo al 99 % para la diferencia
(de −1,57 a −0,30 mm) no incluye el cero.

Un aviso: la prueba de normalidad sale justo en el límite para el grupo temprano
(p = 0,049). Con 30 cráneos por grupo se aplica igualmente la t, como se razona en el
informe.

El notebook está en `src/`, los datos en `data/`, el informe en `reports/` y la gráfica
en `images/`. Python con pandas, SciPy y Seaborn.
