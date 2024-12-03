
# Análisis de Factores Asociados al Estado de Actividad Laboral en Refugiados y Migrantes Venezolanos en el Perú: Un Enfoque Predictivo Utilizando Machine Learning

Este repositorio presenta un análisis detallado de los factores que afectan el estado de actividad laboral de los refugiados y migrantes venezolanos en Perú, utilizando enfoques predictivos con **Machine Learning**. A través del uso de modelos avanzados, este trabajo busca identificar las variables clave que impactan la integración laboral de los migrantes en el mercado peruano.

## Descripción del Proyecto

### Introducción
En 2022, Perú albergó a **1,078,854 personas venezolanas**, con un aumento del **41%** en la población migrante desde 2018. Este fenómeno de migración ha tenido un impacto significativo en las principales áreas urbanas del Perú, con Lima y Callao concentrando el **82.5%** de la población venezolana. Este estudio busca entender las dinámicas laborales de los migrantes en el país, particularmente los factores que influyen en su participación en el mercado laboral.

### Preguntas de Investigación

1. ¿Cuál es el modelo de **Machine Learning** que mejor predice el estado de actividad laboral en refugiados y migrantes venezolanos en el Perú en 2022?
2. ¿Cuáles son las características más importantes asociadas al estado de actividad laboral en estos migrantes?

### Métodos Utilizados
- **Regresión Logística**
- **Lasso**
- **Ridge**
- **Elastic Net**
- **Random Forest**
- **Boosted Trees**

Cada uno de estos métodos se aplicó a una serie de **806 variables** recogidas de diversas fuentes, lo que permitió identificar los patrones y relaciones que determinan la actividad laboral de los migrantes.

### Resultados Preliminares

#### Variables Más Relevantes para la Predicción:
- **Sexo**
- **Edad**
- **Experiencia laboral previa**
- **Capacidad de la municipalidad**
- **Necesidad alimentaria no cubierta**

#### Modelos Predictivos Más Eficientes:
Los modelos de **Boosted Trees** y **Random Forest** mostraron el mejor desempeño en términos de precisión y capacidad predictiva.

### Visualizaciones
Se han creado varias visualizaciones interactivas y mapas para mostrar los resultados del análisis:
- **Mapa de Porcentaje de Trabajo por Distrito** en Lima
- **Clasificación de Distritos** con trabajo muy bajo y muy alto
- **Distribución de Necesidad Alimentaria No Cubierta** por distrito

## Requerimientos

Para ejecutar este análisis, es necesario tener las siguientes bibliotecas en R:

- `tidyverse`
- `sf`
- `ggplot2`
- `leaflet`
- `classInt`
- `spdep`
- `corrplot`
- `gt`

Puedes instalar todas estas bibliotecas usando el siguiente comando:

```r
install.packages(c("tidyverse", "sf", "ggplot2", "leaflet", "classInt", "spdep", "corrplot", "gt"))
```

## Instrucciones para la Ejecución

1. **Carga de datos**: Los datos se encuentran en el archivo `full_data_2022.csv` y los shapefiles en el directorio `./mapas/data-mapas/`.
2. **Generación de Mapas**: Utilizando el paquete `ggplot2` y `leaflet`, se generarán mapas de la distribución de trabajo y necesidad alimentaria por distrito.
3. **Análisis Predictivo**: El análisis predictivo utiliza técnicas de **Machine Learning**, incluyendo el preprocesamiento de datos, tratamiento de missing values, y entrenamiento de modelos.

## Metodología

### 1. Preprocesamiento de Datos

- **Filtro de valores faltantes**: Se eliminaron variables con más del 10% de valores faltantes.
- **Imputación**: Se utilizó la media para variables numéricas y la moda para variables categóricas.
- **Eliminación de outliers**: Se identificaron y eliminaron outliers en las variables clave.

### 2. Variable Dependiente

La variable dependiente se basó en la pregunta sobre el estado de actividad laboral de los migrantes: **¿Tuvo trabajo la semana pasada?**.

### 3. Métodos de Muestreo

Para balancear las clases en los datos se utilizaron los siguientes métodos:
- **SMOTE TOMEK**
- **SMOTE**
- **Naive Random Sampling (NRS)**

### 4. Resultados de Modelos

Los modelos fueron evaluados utilizando las siguientes métricas:
- **Exactitud Global (Accuracy)**
- **Área Bajo la Curva ROC (ROC AUC)**
- **F1 Score Global**

Los modelos más efectivos fueron los basados en **Boosted Trees** y **Random Forest**, con un **F1 Score** global cercano a 0.81.

## Conclusiones

1. **Modelos Predictivos**: Los modelos basados en árboles de decisión, como **Boosted Trees**, fueron los más efectivos para predecir el estado de actividad laboral de los migrantes venezolanos.
2. **Factores Clave**: Las variables como **sexo**, **edad**, y la **experiencia laboral previa** fueron determinantes para predecir la participación laboral.
3. **Políticas Públicas**: Es crucial que las políticas públicas se enfoquen en los factores identificados, como el apoyo a la validación de títulos y la integración laboral, para mejorar la inclusión económica y social de los migrantes.

## Fuentes de Datos

- **Instituto Nacional de Estadística e Informática (INEI)**. (2023). *Encuesta Nacional de Programas de Educación y Evaluación del Perú (ENPOVE)*.
- **Registro Nacional de Municipalidades (RENAMU)**. (2023). *Reporte de capacidades municipales en el Perú*.
- **Ministerio de Economía y Finanzas (MEF)**. (2023). *Sistema Integrado de Administración Financiera (SIAF)*.
- **ACNUR**. (2023). *Migrantes y refugiados venezolanos: Barreras legales y sociales*.
- **Távarez, R., & Alcázar, R.** (2023). *Obstáculos para la validación de títulos profesionales en migrantes venezolanos*. Revista de Estudios Sociales, 35(2), 102–115.

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulte el archivo `LICENSE` para más detalles.

