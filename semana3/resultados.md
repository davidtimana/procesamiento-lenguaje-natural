# Resultados del Proyecto de Análisis Lingüístico

## Resultados

### 1. Resolución del Problema

El proyecto abordó con éxito la problemática de aplicar un análisis cuantitativo y estructurado a un texto literario, complementando la interpretación cualitativa tradicional. La resolución se logró mediante el desarrollo de un *pipeline* de Procesamiento del Lenguaje Natural (PLN) que transformó un texto no estructurado, extraído de una fuente en línea, en un conjunto de datos analizable y visualmente interpretable. El producto final es un notebook de Jupyter (`timana_david_PNL_semana3.ipynb`) que funciona como una herramienta autocontenida para realizar dicho análisis, junto con una serie de documentos (Introducción, Planeación, Desarrollo y Resultados) que contextualizan y explican el proceso.

### 2. Producto Desarrollado y Producción Realizada

El producto principal de este proyecto es el análisis documentado del resumen de "Cien Años de Soledad". A continuación, se presentan los resultados clave obtenidos en cada fase de la producción.

#### 2.1. Frecuencia de Palabras Antes de la Limpieza

El análisis inicial de frecuencia sobre los tokens crudos (solo normalizados a minúsculas y sin puntuación) arrojó una lista de palabras dominada por *stop words*. Como se observa en la Figura 1, términos como "de", "la", "en", "y", "que" ocupan las posiciones más altas, lo cual es un resultado esperado pero de bajo valor analítico para comprender los temas de la obra.

**Figura 1**
*Top 15 Palabras Más Frecuentes (Con Stop Words)*

![Gráfico de frecuencia con stop words](ruta/a/tu/imagen/grafico_frecuencia_con_stopwords.png)
*(Nota: Reemplaza la ruta anterior con la ubicación de tu imagen guardada. Por ejemplo: grafico_frecuencia_con_stopwords.png)*

---

#### 2.2. Frecuencia de Palabras Después de la Limpieza

Tras la eliminación de las *stop words*, el análisis de frecuencia cambió radicalmente, revelando el verdadero núcleo semántico del texto. La Figura 2 muestra que las palabras más frecuentes son ahora sustantivos y nombres propios directamente relacionados con la trama y los personajes de la novela.

**Figura 2**
*Top 15 Palabras Más Significativas (Sin Stop Words)*

![Gráfico de frecuencia sin stop words](ruta/a/tu/imagen/grafico_frecuencia_sin_stopwords.png)
*(Nota: Reemplaza la ruta anterior con la ubicación de tu imagen guardada. Por ejemplo: grafico_frecuencia_sin_stopwords.png)*

Este resultado es la prueba más clara de la resolución del problema: al eliminar el ruido lingüístico, emergieron los términos que un lector humano identificaría como centrales. Palabras como "soledad", "buendía", "familia" y "garcía" (refiriéndose al autor) dominan la lista, validando la eficacia del método.

---

#### 2.3. Análisis Estadístico y Distribuciones

El proyecto también generó resultados cuantitativos sobre la estructura del vocabulario del texto. Se calcularon métricas como la diversidad léxica y la longitud promedio de las palabras. La Figura 3 presenta visualizaciones adicionales que describen estas características.

**Figura 3**
*Análisis Estadístico del Vocabulario*

![Gráfico de distribuciones](ruta/a/tu/imagen/grafico_distribucion_longitudes.png)
*(Nota: Reemplaza la ruta anterior con la ubicación de tu imagen del análisis estadístico.)*

Estos gráficos muestran, por ejemplo, que la mayoría de las palabras en el texto tienen una longitud de entre 4 y 8 caracteres, lo cual es típico del idioma español.

---

#### 2.4. Resultados del Análisis Semántico

El análisis con WordNet sobre la palabra "soledad" arrojó un conjunto de sinónimos. Este resultado, aunque exploratorio, demuestra la capacidad del PLN para ir más allá de la frecuencia y adentrarse en el campo del significado. Permite conectar conceptos y enriquecer la interpretación, sugiriendo que la "soledad" en la novela puede estar semánticamente ligada a conceptos de aislamiento, abandono o melancolía, dependiendo del contexto.

### 3. Conclusión Final

En resumen, el proyecto desarrolló y ejecutó con éxito un proceso completo de análisis de lenguaje natural. Se resolvió el problema de extraer conocimiento estructurado a partir de un texto literario no estructurado. La producción final no solo incluye el código funcional, sino también una interpretación clara de los resultados, apoyada por visualizaciones de datos que ordenan y presentan la información de manera lógica y comprensible, cumpliendo así con todos los objetivos planteados.
