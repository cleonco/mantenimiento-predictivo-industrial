# Predicción de fallas en maquinaria industrial

## Información del autor

**Nombre:** [Cristian Alejandro Leon Cordero]  
**Carrera:** Ingeniería Industrial  
**Materia:** [DataXperience]  
**Institución:** [Universidad EAN]  
**Fecha:** [21 de noviembre del 2026]

---

## Descripción del proyecto

Este proyecto aplica técnicas de ciencia de datos para analizar las condiciones operativas de maquinaria industrial y predecir la ocurrencia de fallas.

El análisis utiliza variables como la temperatura del aire, la temperatura del proceso, la velocidad de rotación, el torque y el desgaste de la herramienta. Estas variables se utilizan para identificar patrones relacionados con posibles fallas de una máquina.

El proyecto busca mostrar cómo las herramientas de análisis de datos y aprendizaje automático pueden apoyar la toma de decisiones en procesos industriales.

---

## Relación con Ingeniería Industrial

Este proyecto se relaciona con Ingeniería Industrial porque el mantenimiento predictivo puede ayudar a reducir paradas no planificadas, mejorar la disponibilidad de los equipos, optimizar los recursos de mantenimiento y favorecer la continuidad de los procesos productivos.

En un contexto profesional, un modelo predictivo podría apoyar la identificación de máquinas con mayor riesgo de falla y ayudar a priorizar las inspecciones o actividades de mantenimiento.

---

## Pregunta de investigación

¿Es posible identificar el riesgo de falla de una máquina utilizando sus condiciones operativas?

---

## Objetivo general

Analizar las condiciones operativas de maquinaria industrial y construir un modelo de clasificación que permita predecir posibles fallas.

---

## Objetivos específicos

- Explorar las variables contenidas en el conjunto de datos.
- Identificar valores faltantes, duplicados y posibles inconsistencias.
- Analizar la relación entre las variables operativas y la ocurrencia de fallas.
- Construir un modelo de aprendizaje automático para clasificar las máquinas.
- Evaluar el desempeño del modelo mediante diferentes métricas.
- Analizar la posible aplicación del modelo en mantenimiento industrial.

---

## Dataset utilizado

El conjunto de datos utilizado es el **AI4I 2020 Predictive Maintenance Dataset**.

El dataset es sintético, pero fue diseñado para representar un contexto industrial de mantenimiento predictivo. Contiene información sobre diferentes condiciones de funcionamiento de máquinas y un indicador que señala si ocurrió una falla.

Las variables principales son:

- **Tipo de producto:** categoría del producto fabricado.
- **Temperatura del aire:** temperatura del ambiente en grados Celsius.
- **Temperatura del proceso:** temperatura del proceso industrial en grados Celsius.
- **Velocidad de rotación:** velocidad de la máquina en revoluciones por minuto.
- **Torque:** fuerza de giro de la máquina en newton-metro.
- **Desgaste de la herramienta:** tiempo de desgaste de la herramienta en minutos.
- **Falla de máquina:** variable objetivo que indica si ocurrió una falla.

---

## Metodología

El proyecto se desarrolló en las siguientes etapas:

### Etapa 1: Exploración y preparación de datos

Se revisaron las dimensiones del dataset, los tipos de variables, los valores faltantes, los registros duplicados y las estadísticas descriptivas.

También se eliminaron las variables identificadoras que no aportaban información operativa y se revisaron posibles variables que pudieran generar fuga de información.

### Etapa 2: Análisis exploratorio y modelado

Se elaboraron gráficos para analizar la distribución de las fallas y comparar las condiciones operativas de las máquinas con y sin falla.

Posteriormente, se construyó un modelo de clasificación utilizando el algoritmo Random Forest.

### Etapa 3: Evaluación y aplicación profesional

El modelo se evaluó mediante exactitud, precisión, sensibilidad, F1-score y AUC. Finalmente, se interpretaron los resultados y se analizaron sus posibles aplicaciones en el área de mantenimiento industrial.

---

## Limpieza y preparación de los datos

Durante la preparación de los datos se realizaron las siguientes actividades:

- Revisión de valores faltantes.
- Revisión y eliminación de registros duplicados.
- Eliminación de identificadores.
- Conversión y revisión de variables categóricas.
- Separación de la variable objetivo.
- División de los datos en conjuntos de entrenamiento y prueba.
- Aplicación de técnicas de preprocesamiento antes del entrenamiento.

Las variables que describen directamente tipos específicos de falla fueron revisadas para evitar fuga de información en el modelo.

Las temperaturas originales estaban expresadas en Kelvin. Para facilitar la interpretación en Ingeniería Industrial, se crearon nuevas columnas en grados Celsius utilizando la fórmula:

Temperatura en Celsius = Temperatura en Kelvin - 273.15 

No se encontraron registros duplicados en el conjunto de datos.

---

## Modelo utilizado

Se utilizó un modelo de clasificación **Random Forest**.

Este modelo fue seleccionado porque puede analizar relaciones no lineales entre las condiciones de operación y la ocurrencia de fallas. Además, permite obtener una estimación de la importancia de las variables utilizadas por el modelo.

Para el entrenamiento se dividieron los datos de la siguiente manera:

- **80 %** para entrenamiento.
- **20 %** para prueba.
- `random_state = 42`.
- División estratificada para conservar la proporción de máquinas con y sin falla.

---

## Resultados

Los resultados deben completarse después de ejecutar el cuaderno de Google Colab.

| Métrica | Resultado |
|---|---:|
| Exactitud | [0.979000] |
| Precisión | [0.933333] |
| Sensibilidad | [0.411765] |
| F1-score | [0.571429] |
| AUC | [0.964457] |

El modelo obtuvo una exactitud de **[97%]**, lo que representa la proporción general de predicciones correctas.

La precisión fue de **[93%]**, indicando qué proporción de las máquinas clasificadas como defectuosas realmente presentó una falla.

La sensibilidad fue de **[41%]**. Esta métrica es importante en mantenimiento predictivo porque indica la capacidad del modelo para detectar máquinas que realmente presentan una falla.

El F1-score fue de **[57%]**, combinando la precisión y la sensibilidad en una sola medida.

El AUC fue de **[96%]**, lo que permite evaluar la capacidad general del modelo para distinguir entre máquinas con y sin falla.

Desde el punto de vista industrial, la sensibilidad es importante porque un falso negativo podría representar una falla no detectada y ocasionar una parada no planificada. Sin embargo, también deben considerarse los falsos positivos, ya que podrían generar inspecciones o mantenimientos innecesarios.

---

## Gráficos principales

### Distribución de fallas

![Distribución de fallas](resultados/distribucion_fallas.png)

### Matriz de confusión

![Matriz de confusión](resultados/matriz_confusion.png)

### Importancia de variables

![Importancia de variables](resultados/importancia_variables.png)

---

## Aplicación profesional

En un contexto industrial, el modelo podría utilizarse como una herramienta de apoyo para priorizar inspecciones, planificar actividades de mantenimiento y detectar máquinas que presenten condiciones operativas asociadas con un mayor riesgo de falla.

La aplicación de este tipo de modelos podría contribuir a reducir tiempos muertos, mejorar la disponibilidad de los equipos y optimizar los recursos asignados al mantenimiento.

Sin embargo, el modelo no debe utilizarse de manera aislada. Antes de implementarlo en una planta real, sería necesario validarlo con datos reales, comparar sus resultados con la experiencia de los técnicos y considerar los costos de los falsos positivos y falsos negativos.

---

## Conclusiones

El proyecto permitió aplicar un flujo completo de ciencia de datos, incluyendo la exploración, limpieza, transformación, visualización y modelado de datos.

El análisis mostró la importancia de preparar correctamente la información antes de entrenar un modelo. También permitió comprender que la evaluación debe realizarse utilizando varias métricas y considerando el contexto del problema.

Desde la perspectiva de Ingeniería Industrial, el aprendizaje automático puede apoyar el mantenimiento predictivo y la toma de decisiones relacionadas con la operación de los equipos.

Los resultados obtenidos deben considerarse como una aproximación académica y no como una solución lista para implementarse directamente en una planta industrial.

---

## Limitaciones

El dataset utilizado es sintético y no representa necesariamente el comportamiento de una planta industrial específica.

Además, el modelo no fue validado con información real de una empresa. Por esta razón, sus resultados no deben generalizarse automáticamente a otros procesos, máquinas o industrias.

La importancia de una variable no demuestra que dicha variable sea la causa de una falla. Los resultados representan asociaciones utilizadas por el modelo y no relaciones causales definitivas.

---

## Cuaderno de Google Colab

El cuaderno con el código completo del proyecto se encuentra en la carpeta `notebook/`.

También puede abrirse directamente en Google Colab mediante el siguiente enlace:

[ Abrir cuaderno en Google Colab ](https://colab.research.google.com/drive/1skGYx9ni7Jb7Xp5VtmU8XHpwK2_HdWLc?usp=sharing)

---

## Presentación

La presentación de apoyo se encuentra en la carpeta `presentacion/`.

Archivo:

[presentacion_mantenimiento_predictivo.pdf](presentacion/presentacion_mantenimiento_predictivo.pdf)

---

## Video de presentación

El video de presentación puede consultarse en el siguiente enlace:

[ Ver video de presentación ](PEGAR_AQUÍ_EL_ENLACE_DEL_VIDEO)

**Duración del video:** [Escribe la duración en minutos y segundos]

---

## Estructura del repositorio

```Text
mantenimiento-predictivo-industrial/
│
├── README.md
│
├── datos/
│   ├── README.md
│   └── ai4i2020.csv
│
├── notebook/
│   └── mantenimiento_predictivo.ipynb
│
├── presentacion/
│   └── presentacion_mantenimiento_predictivo.pdf
│
├── resultados/
│   ├── distribucion_fallas.png
│   ├── matriz_confusion.png
│   ├── matriz_correlacion.png
│   └── importancia_variables.png
│
└── video/
    └── enlace_video.txt
