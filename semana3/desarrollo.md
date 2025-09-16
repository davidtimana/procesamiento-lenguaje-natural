# Desarrollo del Análisis de Lenguaje Natural

## Desarrollo

### 1. Contextualización del Problema

El análisis de un texto literario denso como "Cien Años de Soledad" presenta una serie de problemáticas inherentes cuando se aborda desde una perspectiva computacional. El texto en su estado natural es una secuencia de caracteres no estructurada, cargada de elementos que, si bien son esenciales para la lectura humana, constituyen "ruido" para un análisis cuantitativo. Las problemáticas principales que se deben resolver son:

*   **Adquisición de Datos:** El texto no está disponible localmente, por lo que se requiere un método para extraerlo de una fuente externa (una página web).
*   **Ruido Lingüístico:** El texto contiene signos de puntuación, mayúsculas y minúsculas, y palabras funcionales (artículos, preposiciones) que pueden distorsionar las estadísticas de frecuencia.
*   **Ambigüedad Semántica:** Un análisis basado únicamente en el conteo de palabras no puede capturar las relaciones de significado entre ellas (sinonimia, antonimia).
*   **Interpretación de Resultados:** Los datos numéricos y las listas de palabras por sí solos no son intuitivos y requieren una representación visual para facilitar su comprensión.

A continuación, se presenta la exposición ordenada de las soluciones implementadas y los resultados obtenidos para cada una de estas problemáticas.

### 2. Solución Implementada y Resultados

#### 2.1. Fase de Adquisición y Preparación de Datos

*   **Problemática:** Acceder y preparar el corpus textual para el análisis.
*   **Solución:** Se desarrolló un script en Python utilizando las bibliotecas `urllib` para la conexión y descarga del contenido HTML de la URL de destino, y `BeautifulSoup` para el parseo y la extracción del texto limpio. Este proceso automatizado permitió obtener un corpus textual de **14,189 caracteres**, libre de etiquetas HTML y scripts, listo para el preprocesamiento.
*   **Resultado:** Se obtuvo una base textual coherente y manejable, que sirve como punto de partida para todo el análisis posterior.

#### 2.2. Preprocesamiento del Texto: Tokenización y Normalización

*   **Problemática:** El texto crudo no puede ser analizado directamente. Es necesario descomponerlo en unidades manejables y estandarizarlo.
*   **Solución:** Se aplicaron tres principios fundamentales del procesamiento de lenguaje natural:
    1.  **Tokenización:** Utilizando la función `word_tokenize` de NLTK, con el idioma configurado en español, el texto fue segmentado en una lista de palabras individuales o *tokens*.
    2.  **Eliminación de Puntuación:** Se aplicó un filtro para conservar únicamente los tokens alfabéticos, descartando números y cualquier signo de puntuación.
    3.  **Normalización (Case Folding):** Todos los tokens se convirtieron a minúsculas para asegurar que palabras como "Soledad" y "soledad" fueran tratadas como una única entidad.
*   **Resultado:** Se transformó el texto crudo en una lista estructurada de tokens limpios, lo que redujo la complejidad del vocabulario y preparó los datos para un análisis de frecuencia preciso.

#### 2.3. Análisis de Frecuencia y Eliminación de *Stop Words*

*   **Problemática:** Las palabras más comunes en cualquier idioma (como "de", "la", "que") suelen ser las más frecuentes en un texto, pero carecen de significado temático y sesgan el análisis.
*   **Solución:** Se empleó la lista de *stop words* en español proporcionada por NLTK. Se creó un nuevo listado de tokens filtrando y eliminando todas las palabras contenidas en dicha lista.
*   **Resultados:**
    *   **Antes del filtrado:** El análisis de frecuencia mostraba que las palabras más comunes eran artículos y preposiciones, ocultando los términos verdaderamente relevantes de la obra.
    *   **Después del filtrado:** El análisis de frecuencia reveló un vocabulario mucho más significativo. Palabras como "soledad", "buendía", "familia", "garcía" y "márquez" emergieron como los términos de mayor frecuencia, lo cual está en perfecta consonancia con los temas centrales de la novela. Este resultado valida la eficacia de la eliminación de *stop words* para descubrir el núcleo temático de un texto.

#### 2.4. Exploración Semántica con WordNet

*   **Problemática:** Identificar las relaciones de significado que no son evidentes a través del simple conteo de palabras.
*   **Solución:** Se utilizó la base de datos léxica WordNet, integrada en NLTK, para realizar un análisis de sinonimia. Se seleccionó la palabra "soledad", un término de alta frecuencia y de importancia capital para la novela.
*   **Resultado:** WordNet proporcionó una lista de sinónimos para "soledad". Este proceso demostró cómo el PLN puede trascender el análisis superficial y empezar a explorar la riqueza semántica de un texto. Permite, por ejemplo, agrupar diferentes palabras que apuntan a un mismo concepto, enriqueciendo así la comprensión de los temas.

#### 2.5. Visualización de Datos

*   **Problemática:** La presentación de los resultados en forma de listas o tablas numéricas es poco efectiva para la comunicación de hallazgos.
*   **Solución:** Se utilizó la biblioteca `Matplotlib` para generar apoyos visuales. Se crearon gráficos de barras comparativos que muestran las 15 palabras más frecuentes antes y después de la eliminación de *stop words*.
*   **Resultado:** Las visualizaciones lograron comunicar de manera inmediata y clara el impacto del preprocesamiento en los resultados. El contraste entre los dos gráficos sirve como una poderosa ilustración de cómo la limpieza de datos es fundamental en el PLN para obtener conclusiones significativas. Los gráficos ordenan la información de manera lógica y apoyan visualmente las conclusiones del análisis.
