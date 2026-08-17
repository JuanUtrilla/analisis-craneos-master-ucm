# Contraste de hipótesis sobre anchura craneal en dos periodos históricos

Estudio estadístico completo —descriptivo e inferencial— sobre si la anchura craneal
cambió entre dos periodos de un mismo yacimiento arqueológico. Un caso pequeño y limpio
para aplicar el procedimiento correcto de principio a fin: comprobar los supuestos antes
de aplicar el test, no después.

Desarrollado en el módulo de *Estadística* del Máster en Big Data, Data Science e
Inteligencia Artificial (Universidad Complutense de Madrid, curso 2025-26).

## El problema

60 cráneos medidos en milímetros, repartidos en dos muestras independientes de 30:
**predinástico temprano** y **predinástico tardío**. ¿Hay evidencia de una diferencia real
de medias, o lo observado cabe dentro del azar muestral?

## Procedimiento

El orden importa, porque cada paso condiciona la validez del siguiente:

1. **Análisis descriptivo** — media, mediana, desviación típica, asimetría y curtosis por
   grupo, más diagrama de caja y bigotes.
2. **Contraste de normalidad** — tests de Shapiro-Wilk y Kolmogorov-Smirnov sobre cada
   muestra. Requisito previo del t-test paramétrico.
3. **Contraste de homocedasticidad** — test de Levene para decidir entre la versión de
   varianzas iguales y la corrección de Welch.
4. **Intervalos de confianza** para la diferencia de medias al 90 %, 95 % y 99 %.
5. **t-Student para muestras independientes** y lectura del resultado.

## Resultados

| Grupo | n | Media (mm) | Desv. típica |
|---|---|---|---|
| Predinástico temprano | 30 | 131,53 | 0,82 |
| Predinástico tardío | 30 | 132,47 | 1,01 |

![Diagrama de caja y bigotes](images/caja_bigotes.svg)

- **Diferencia de medias estimada:** −0,933 mm. El intervalo de confianza **no incluye el
  cero ni siquiera al 99 %**, que es la forma robusta de leer el resultado: no depende de
  fijar un umbral arbitrario en el p-valor.
- **t-Student:** t = −3,935 con 58 grados de libertad, p = 0,00023.

**Conclusión:** se rechaza la hipótesis nula de igualdad de medias. Los cráneos del
periodo tardío son, en promedio, en torno a 1 mm más anchos.

Conviene añadir el matiz que el p-valor no da: la diferencia es estadísticamente
significativa, pero **su magnitud es pequeña frente a la dispersión de cada grupo**
(≈0,9 mm de diferencia con desviaciones típicas de 0,8 y 1,0). Significativo no es
sinónimo de relevante, y con n = 30 por grupo la potencia para detectar efectos de este
tamaño es limitada.

## Estructura

| Ruta | Contenido |
|---|---|
| `src/` | Notebook con el análisis completo. |
| `data/` | Datos de partida (Excel). |
| `reports/` | Informe en PDF. |
| `images/` | Gráficas generadas (SVG). |

## Stack

Python · pandas · NumPy · SciPy · Seaborn · Matplotlib

---

**Juan Peñas Utrilla** — [LinkedIn](https://www.linkedin.com/in/juan-penas-utrilla/) · [GitHub](https://github.com/JuanUtrilla)
