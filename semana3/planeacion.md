# Plan de Trabajo: Análisis de Lenguaje Natural en "Cien Años de Soledad"

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
