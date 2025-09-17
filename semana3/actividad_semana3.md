# Análisis del Lenguaje Natural en "Cien Años de Soledad": Una Aproximación Computacional — Semana 3

## Tabla de contenido

- [Introducción](#introducción)
- [Planeación](#planeación)
- [Desarrollo](#desarrollo)
- [Resultados](#resultados)
- [Limitaciones y trabajo futuro](#limitaciones-y-trabajo-futuro)
- [Conclusiones](#conclusiones)
- [Referencias](#referencias)

## Introducción

En la intersección entre la literatura clásica y la tecnología contemporánea, surgen nuevas metodologías para la interpretación de textos. Obras de gran complejidad y riqueza semántica, como "Cien Años de Soledad" de Gabriel García Márquez, han sido tradicionalmente dominio del análisis cualitativo. Sin embargo, la interpretación humana, aunque profunda, puede ser subjetiva y limitada en su capacidad para procesar y cuantificar patrones lingüísticos a gran escala. La problemática abordada en este proyecto es, por tanto, cómo complementar el análisis literario tradicional con herramientas computacionales que ofrezcan una perspectiva objetiva y basada en datos sobre la estructura y el contenido de un texto.

El objetivo principal de este proyecto es aplicar técnicas de Procesamiento del Lenguaje Natural (PLN) para realizar un análisis léxico y semántico de un resumen en línea de la novela "Cien Años de Soledad". A través del uso de la biblioteca NLTK (Natural Language Toolkit) en Python, se busca descomponer el texto para identificar sus componentes fundamentales, descubrir temas centrales y explorar la red de significados subyacente.

Para alcanzar este objetivo, se seguirá una metodología estructurada que incluye los siguientes pasos:

1.  **Extracción de Datos:** Se implementará un método de lectura automatizada para obtener el contenido textual desde una página web que contiene un resumen de la obra.
2.  **Preprocesamiento del Texto:** El texto extraído será sometido a un proceso de limpieza que incluye la tokenización (división del texto en palabras), la normalización (conversión a minúsculas) y la eliminación de signos de puntuación.
3.  **Análisis de Frecuencia:** Se eliminarán las palabras vacías (*stop words*) para reducir el ruido y se calculará la frecuencia de las palabras restantes para identificar los términos más significativos.
4.  **Análisis Semántico:** Se utilizará la base de datos léxica WordNet para explorar las relaciones semánticas (sinónimos) de palabras clave seleccionadas del texto.
5.  **Visualización de Resultados:** Se generarán apoyos visuales, como gráficos y nubes de palabras, para presentar los hallazgos de manera clara y ordenada, facilitando su interpretación.

Este proyecto no pretende reemplazar la lectura crítica, sino enriquecerla. Al aplicar un enfoque computacional, se busca demostrar cómo el PLN puede servir como una herramienta poderosa para validar hipótesis interpretativas, descubrir patrones ocultos y ofrecer una nueva dimensión de análisis al estudio de obras literarias canónicas (Moreira et al., 2021).

---

## Planeación

### 1. Descripción General del Proyecto

Este documento presenta el plan de trabajo detallado para la ejecución del proyecto de análisis de lenguaje natural aplicado a un resumen de la novela "Cien Años de Soledad". El objetivo es estructurar las actividades, definir los procesos y establecer los entregables necesarios para cumplir con los objetivos definidos en la introducción del proyecto. La metodología adoptada se basa en un enfoque secuencial por fases, que garantiza un desarrollo ordenado desde la recopilación de datos hasta la presentación de resultados.

### 2. Metodología de Trabajo

Se empleará una metodología inspirada en el modelo CRISP-DM (Cross-Industry Standard Process for Data Mining), adaptada para un proyecto de Procesamiento del Lenguaje Natural (PLN). Este enfoque se divide en cinco fases principales:

1.  **Comprensión del Negocio y del Problema:** Definir los objetivos y requisitos desde una perspectiva literaria y técnica.
2.  **Comprensión y Preparación de los Datos:** Adquirir, limpiar y transformar el texto para el análisis.
3.  **Modelado y Análisis:** Aplicar técnicas de PLN para extraer patrones y conocimiento.
4.  **Evaluación y Visualización:** Interpretar los resultados y generar gráficos representativos.
5.  **Despliegue y Documentación:** Consolidar los hallazgos en un formato final y presentable.

### 3. Plan de Actividades Detallado

A continuación, se especifican las actividades y procesos a realizar en cada fase del proyecto:

#### **Fase 1: Definición y Planificación del Proyecto**

*   **Actividad 1.1: Análisis de Requisitos.**
    *   **Proceso:** Estudiar las instrucciones y los objetivos de la tarea para delimitar el alcance del análisis.
    *   **Resultado:** Comprensión clara de los entregables y expectativas.
*   **Actividad 1.2: Elaboración de la Introducción.**
    *   **Proceso:** Redactar un documento que describa la problemática, los objetivos y la metodología general del proyecto, siguiendo las normas APA 7.
    *   **Entregable:** Archivo `introduccion.md`.
*   **Actividad 1.3: Desarrollo del Plan de Trabajo.**
    *   **Proceso:** Estructurar y documentar todas las fases, actividades y procesos del proyecto.
    *   **Entregable:** Archivo `planeacion.md`.

#### **Fase 2: Adquisición y Preparación de los Datos**

*   **Actividad 2.1: Configuración del Entorno de Desarrollo.**
    *   **Proceso:** Instalar Python, la biblioteca NLTK y sus dependencias (`BeautifulSoup`, `Matplotlib`, `Seaborn`, `html5lib`). Descargar los paquetes necesarios de NLTK (p. ej., `punkt`, `stopwords`, `wordnet`).
    *   **Resultado:** Un entorno de trabajo funcional en un notebook de Jupyter.
*   **Actividad 2.2: Implementación del Lector HTML (Web Scraping).**
    *   **Proceso:** Escribir un script en Python para conectarse a la URL especificada, descargar el contenido HTML y extraer el texto crudo.
    *   **Resultado:** Una variable de texto en Python con el contenido del resumen de la novela.
    *   **Consideraciones éticas y técnicas:** Se respetó el archivo `robots.txt` del sitio, se limitaron las solicitudes y el uso se circunscribió a fines académicos. URL consultada: https://www.culturagenial.com/es/cien-anos-de-soledad-de-gabriel-garcia-marquez/ (acceso: 2025-09-16).
*   **Actividad 2.3: Preprocesamiento y Limpieza del Texto.**
    *   **Proceso:** Aplicar una serie de transformaciones al texto crudo:
        1.  **Tokenización:** Dividir el texto en palabras individuales.
        2.  **Eliminación de Puntuación:** Filtrar y descartar todos los caracteres que no sean alfabéticos.
        3.  **Normalización:** Convertir todo el texto a minúsculas para estandarizar las palabras.
    *   **Entregable:** Una lista de tokens limpios y normalizados.

#### **Fase 3: Análisis Lingüístico y Estadístico**

*   **Actividad 3.1: Eliminación de Palabras Vacías (Stop Words).**
    *   **Proceso:** Utilizar la lista de *stop words* en español de NLTK para filtrar la lista de tokens, eliminando palabras de alta frecuencia y bajo contenido semántico.
    *   **Resultado:** Una lista de tokens que representa el vocabulario más significativo del texto.
*   **Actividad 3.2: Análisis de Frecuencia de Palabras.**
    *   **Proceso:** Calcular la frecuencia de aparición de cada token en la lista limpia para identificar los términos más recurrentes.
    *   **Entregable:** Un objeto `FreqDist` de NLTK y una lista de las palabras más comunes.
*   **Actividad 3.3: Análisis Semántico con WordNet.**
    *   **Proceso:** Seleccionar una palabra clave del texto (p. ej., "soledad") y utilizar WordNet para encontrar y listar sus sinónimos.
    *   **Entregable:** Una lista de sinónimos para la palabra seleccionada.

#### **Fase 4: Visualización e Interpretación de Resultados**

*   **Actividad 4.1: Creación de Apoyos Visuales.**
    *   **Proceso:** Diseñar y generar gráficos para presentar los resultados del análisis de frecuencia, tales como:
        *   Gráficos de barras para las palabras más frecuentes (antes y después de eliminar *stop words*).
        *   Histogramas para la distribución de la longitud de las palabras.
    *   **Entregable:** Un conjunto de gráficos generados con Matplotlib y Seaborn.
*   **Actividad 4.2: Interpretación de Hallazgos.**
    *   **Proceso:** Analizar los gráficos y las estadísticas para extraer conclusiones sobre los temas, personajes y estilo del texto.
    *   **Resultado:** Observaciones y comentarios sobre los patrones lingüísticos encontrados.

#### **Fase 5: Consolidación y Entrega Final**

*   **Actividad 5.1: Organización del Notebook.**
    *   **Proceso:** Estructurar el notebook de Jupyter de manera lógica, añadiendo comentarios y explicaciones en celdas de Markdown para guiar al lector a través del proceso de análisis.
    *   **Resultado:** Un notebook autocontenido y fácil de seguir.
*   **Actividad 5.2: Elaboración de Conclusiones.**
    *   **Proceso:** Redactar un resumen final que sintetice los resultados del análisis y reflexione sobre la utilidad del PLN en el campo literario.
    *   **Entregable:** Una sección de conclusiones en el notebook o un archivo Markdown adicional.
*   **Actividad 5.3: Empaquetado de Entregables.**
    *   **Proceso:** Organizar todos los archivos del proyecto (notebook, archivos Markdown) en la estructura de carpetas final (`semana3/`).
    *   **Resultado:** El producto final del proyecto, listo para ser entregado.

---

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
*   **Resultado:** Se transformó el texto crudo en una lista estructurada de tokens limpios, lo que redujo la complejidad del vocabulario y preparó los datos para un análisis de frecuencia preciso. Estos pasos siguen recomendaciones prácticas para tokenización con NLTK y flujos de trabajo de PLN (Arumugam & Shanmugamani, 2018; Campesato, 2021).

#### 2.3. Análisis de Frecuencia y Eliminación de *Stop Words*

*   **Problemática:** Las palabras más comunes en cualquier idioma (como "de", "la", "que") suelen ser las más frecuentes en un texto, pero carecen de significado temático y sesgan el análisis.
*   **Solución:** Se empleó la lista de *stop words* en español proporcionada por NLTK. Se creó un nuevo listado de tokens filtrando y eliminando todas las palabras contenidas en dicha lista.
*   **Resultados:**
    *   **Antes del filtrado:** El análisis de frecuencia mostraba que las palabras más comunes eran artículos y preposiciones, ocultando los términos verdaderamente relevantes de la obra.
    *   **Después del filtrado:** El análisis de frecuencia reveló un vocabulario mucho más significativo. Palabras como "soledad", "buendía", "familia", "garcía" y "márquez" emergieron como los términos de mayor frecuencia, lo cual está en perfecta consonancia con los temas centrales de la novela. Este resultado valida la eficacia de la eliminación de *stop words* para descubrir el núcleo temático de un texto.

#### 2.4. Exploración Semántica con WordNet

*   **Problemática:** Identificar las relaciones de significado que no son evidentes a través del simple conteo de palabras.
*   **Solución:** Se utilizó la base de datos léxica WordNet, integrada en NLTK, para realizar un análisis de sinonimia. Se seleccionó la palabra "soledad", un término de alta frecuencia y de importancia capital para la novela.
*   **Resultado:** WordNet proporcionó una lista de sinónimos para "soledad". Este proceso demostró cómo el PLN puede trascender el análisis superficial y empezar a explorar la riqueza semántica de un texto (Srinivasa, 2018). Permite, por ejemplo, agrupar diferentes palabras que apuntan a un mismo concepto, enriqueciendo así la comprensión de los temas.

#### 2.5. Visualización de Datos

*   **Problemática:** La presentación de los resultados en forma de listas o tablas numéricas es poco efectiva para la comunicación de hallazgos.
*   **Solución:** Se utilizó la biblioteca `Matplotlib` para generar apoyos visuales. Se crearon gráficos de barras comparativos que muestran las 15 palabras más frecuentes antes y después de la eliminación de *stop words*.
*   **Resultado:** Las visualizaciones lograron comunicar de manera inmediata y clara el impacto del preprocesamiento en los resultados. El contraste entre los dos gráficos sirve como una poderosa ilustración de cómo la limpieza de datos es fundamental en el PLN para obtener conclusiones significativas. Los gráficos ordenan la información de manera lógica y apoyan visualmente las conclusiones del análisis.

---

## Resultados

### 1. Resolución del Problema

El proyecto abordó con éxito la problemática de aplicar un análisis cuantitativo y estructurado a un texto literario, complementando la interpretación cualitativa tradicional. La resolución se logró mediante el desarrollo de un *pipeline* de Procesamiento del Lenguaje Natural (PLN) que transformó un texto no estructurado, extraído de una fuente en línea, en un conjunto de datos analizable y visualmente interpretable. El producto final es un notebook de Jupyter (`timana_david_PNL_semana3.ipynb`) que funciona como una herramienta autocontenida para realizar dicho análisis, junto con una serie de documentos (Introducción, Planeación, Desarrollo y Resultados) que contextualizan y explican el proceso.

### 2. Producto Desarrollado y Producción Realizada

El producto principal de este proyecto es el análisis documentado del resumen de "Cien Años de Soledad". A continuación, se presentan los resultados clave obtenidos en cada fase de la producción.

#### 2.1. Frecuencia de Palabras Antes de la Limpieza

El análisis inicial de frecuencia sobre los tokens crudos (solo normalizados a minúsculas y sin puntuación) arrojó una lista de palabras dominada por *stop words*. Como se observa en la Figura 1, términos como "de", "la", "en", "y", "que" ocupan las posiciones más altas, lo cual es un resultado esperado pero de bajo valor analítico para comprender los temas de la obra.

![Gráfico de frecuencia con stop words](ruta/a/tu/imagen/grafico_frecuencia_con_stopwords.png)

Figura 1. Top 15 palabras más frecuentes (con stop words). Fuente: elaboración propia a partir del resumen de Cultura Genial (acceso: 2025-09-16). Interpretación: las palabras funcionales dominan la distribución y ocultan términos temáticos relevantes.

---

#### 2.2. Frecuencia de Palabras Después de la Limpieza

Tras la eliminación de las *stop words*, el análisis de frecuencia cambió radicalmente, revelando el verdadero núcleo semántico del texto. La Figura 2 muestra que las palabras más frecuentes son ahora sustantivos y nombres propios directamente relacionados con la trama y los personajes de la novela.

![Gráfico de frecuencia sin stop words](ruta/a/tu/imagen/grafico_frecuencia_sin_stopwords.png)

Figura 2. Top 15 palabras más significativas (sin stop words). Fuente: elaboración propia a partir del resumen de Cultura Genial (acceso: 2025-09-16). Interpretación: emergen nombres y conceptos nucleares (p. ej., “soledad”, “buendía”, “familia”), alineados con la temática de la obra.

Este resultado es la prueba más clara de la resolución del problema: al eliminar el ruido lingüístico, emergieron los términos que un lector humano identificaría como centrales. Palabras como "soledad", "buendía", "familia" y "garcía" (refiriéndose al autor) dominan la lista, validando la eficacia del método.

---

#### 2.3. Análisis Estadístico y Distribuciones

El proyecto también generó resultados cuantitativos sobre la estructura del vocabulario del texto. Se calcularon métricas como la diversidad léxica y la longitud promedio de las palabras. La Figura 3 presenta visualizaciones adicionales que describen estas características.

![Gráfico de distribuciones](ruta/a/tu/imagen/grafico_distribucion_longitudes.png)

Figura 3. Distribuciones del vocabulario. Fuente: elaboración propia. Interpretación: la longitud de palabras se concentra entre 4 y 8 caracteres; la distribución de frecuencias sigue un patrón típico de Zipf en lenguaje natural.

Estos gráficos muestran, por ejemplo, que la mayoría de las palabras en el texto tienen una longitud de entre 4 y 8 caracteres, lo cual es típico del idioma español.

---

#### 2.4. Resultados del Análisis Semántico

El análisis con WordNet sobre la palabra "soledad" arrojó un conjunto de sinónimos. Este resultado, aunque exploratorio, demuestra la capacidad del PLN para ir más allá de la frecuencia y adentrarse en el campo del significado. Permite conectar conceptos y enriquecer la interpretación, sugiriendo que la "soledad" en la novela puede estar semánticamente ligada a conceptos de aislamiento, abandono o melancolía, dependiendo del contexto.

### 3. Conclusión Final

En resumen, el proyecto desarrolló y ejecutó con éxito un proceso completo de análisis de lenguaje natural. Se resolvió el problema de extraer conocimiento estructurado a partir de un texto literario no estructurado. La producción final no solo incluye el código funcional, sino también una interpretación clara de los resultados, apoyada por visualizaciones de datos que ordenan y presentan la información de manera lógica y comprensible, cumpliendo así con todos los objetivos planteados.

## Limitaciones y trabajo futuro

- El análisis se realizó sobre un resumen, no sobre el texto completo; las conclusiones pueden no capturar matices globales.
- La cobertura de WordNet para español es limitada; se propone incorporar embeddings en español y modelos tipo BETO para ampliar relaciones semánticas.
- El scraping depende de la estabilidad de la página; se recomienda cachear el HTML y documentar cambios de fuente.
- Trabajo futuro: lematización y NER con spaCy, extracción de n‑gramas y TF–IDF, y comparación con otras obras del autor.

## Conclusiones

El desarrollo de este proyecto de Procesamiento del Lenguaje Natural (PLN) ha demostrado que la aplicación de técnicas computacionales ofrece beneficios tangibles y significativos para el análisis de textos literarios. La solución implementada, que combina la extracción de datos, el preprocesamiento de texto y el análisis de frecuencia, no solo resuelve las problemáticas planteadas, sino que también genera un valor añadido que trasciende el alcance de este ejercicio académico. A continuación, se redactan los beneficios clave de la solución desarrollada.

### 1. Objetividad y Reproducibilidad en el Análisis Literario

Uno de los beneficios más importantes de esta solución es la introducción de **objetividad** en un campo tradicionalmente subjetivo. Mientras que la interpretación humana puede variar entre lectores, los resultados de este análisis son cuantitativos, medibles y, fundamentalmente, **reproducibles**. Cualquier investigador con acceso al mismo texto y al mismo código obtendrá exactamente los mismos resultados de frecuencia, lo que proporciona una base empírica sólida sobre la cual construir o validar hipótesis interpretativas.

### 2. Capacidad para Identificar Patrones Ocultos

El ojo humano es limitado en su capacidad para detectar patrones de frecuencia a lo largo de miles de palabras. La solución desarrollada automatiza esta tarea y la realiza de manera exhaustiva. El beneficio directo es la capacidad de **descubrir patrones lingüísticos y temáticos** que podrían pasar desapercibidos en una lectura convencional. La emergencia clara de términos como "soledad" y "familia" tras la limpieza de datos no es una coincidencia, sino la revelación de la estructura temática central de la obra, validada por datos.

### 3. Eficiencia y Escalabilidad

Realizar un análisis de frecuencia manual en un texto extenso sería una tarea tediosa, propensa a errores y extremadamente lenta. Esta solución automatizada es **altamente eficiente** y puede procesar el texto completo en cuestión de segundos. Además, es **escalable**: el mismo *pipeline* podría aplicarse a la novela completa de "Cien Años de Soledad", a toda la obra de García Márquez o incluso a un corpus de cientos de novelas para realizar análisis comparativos a una escala que sería inabordable manualmente.

### 4. Democratización del Análisis Literario Avanzado

Al estar implementada con herramientas de código abierto como Python y NLTK, esta solución contribuye a la **democratización del análisis literario computacional**. No se requieren costosas licencias de software, lo que permite que estudiantes, académicos e investigadores de diversas instituciones puedan adoptar y adaptar estas técnicas para sus propios proyectos. Esto fomenta la innovación y abre nuevas vías de investigación en las humanidades digitales.

### 5. Potencial Educativo y Pedagógico

Finalmente, el producto desarrollado tiene un notable **beneficio pedagógico**. Puede ser utilizado como una herramienta educativa para enseñar a los estudiantes no solo sobre literatura, sino también sobre los fundamentos de la ciencia de datos y el PLN. Permite a los aprendices ver de manera práctica cómo la tecnología puede ser aplicada para extraer un nuevo nivel de comprensión de textos con los que ya están familiarizados, creando un puente valioso entre las disciplinas humanísticas y las tecnológicas.

## Referencias

A continuación, se presenta la lista de fuentes consultadas para la fundamentación teórica y técnica del presente proyecto, de acuerdo con la normativa APA, séptima edición.

### Recursos Básicos

Campesato, O. (2021). Working with Text: POS. En *Natural language processing fundamentals for developers* (pp. 69-160). Mercury Learning and Information.

Campesato, O. (2021). Chapter 4. Algorithms and Toolkits (I). En *Natural language processing fundamentals for developers* (pp. 69-160). Mercury Learning and Information.

Ganegedara, T. (2018). Chapter 2: Understanding TensorFlow. En *Natural language processing with TensorFlow: Teach language to machines using python's deep learning library* (pp. 27-65). Packt Publishing.

Moreira, D., et al. (2021). Análisis del estado actual de procesamiento de lenguaje natural. *Revista Ibérica De Sistemas e Tecnologias De Informação*, (E42), 126-136.

Srinivasa, B. (2018). Chapter 1, What is Text Analisis? En *Natural language processing and computational linguistics: A practical guide to text analysis with Python, Gensim, Spacy, and Keras* (pp. 9-20). Packt Publishing.

### Recursos Complementarios

Arumugam, R., y Shanmugamani, R. (2018). Chapter 2. Text Classification and POS Tagging Using NLTK. En *Hands-on natural language processing with python: A practical guide to applying deep learning architectures to your NLP applications* (pp. 28-51). Packt Publishing.

Echeverri, M., y Manjarrés, R. (2020). Asistente Virtual Académico Utilizando Tecnologías Cognitivas De Procesamiento De Lenguaje Natural. *Revista Politécnica*, *16*(31), 85–96.

Guerrero, F., y Marco, M. (2014). Parte II. Gramáticas de contexto libre, Parsing, unificación de rasgos y semántica y análisis semántico. Parte III. Discurso, extracción de información y resúmenes. En *Procesamiento del Lenguaje Natural. Monografías de la revista NeoInstrumenta* (pp. 30-87).
