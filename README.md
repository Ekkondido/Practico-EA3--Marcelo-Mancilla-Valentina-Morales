EA3 – Segmentación de Clientes con K-Means

Materia: Machine Learning
Sección: 002D
Año: 2025
Integrantes: Marcelo Mancilla – Valentina Morales

1. Descripción de la técnica utilizada y justificación de su elección

En este proyecto se aplicó K-Means, un algoritmo de aprendizaje no supervisado que agrupa observaciones según su similitud utilizando la distancia euclidiana como métrica principal. El objetivo del análisis es identificar patrones naturales dentro del conjunto de clientes sin utilizar la variable objetivo (TARGET). Esto permite detectar segmentación oculta en la población, comprender perfiles financieros sin necesidad de etiquetas, complementar modelos supervisados como el scoring crediticio e identificar subpoblaciones con comportamientos diferenciados que podrían relacionarse con mayor o menor riesgo.

¿Por qué K-Means?

Elegimos K-Means porque es un método rápido, eficiente y escalable, especialmente adecuado para trabajar con grandes volúmenes de datos. Este algoritmo permite descubrir grupos de clientes que no son evidentes a simple vista, facilitando la detección de patrones ocultos dentro del dataset. Además, es simple de interpretar y fácil de visualizar, lo que lo convierte en una herramienta práctica para el análisis exploratorio. Funciona particularmente bien con variables numéricas estandarizadas como ingresos, montos de crédito o puntajes externos. Finalmente, la implementación se realizó utilizando únicamente el conjunto de entrenamiento, cumpliendo con la instrucción de evitar data leakage y siguiendo correctamente la metodología CRISP-DM.

2. Instrucciones del código

Para ejecutar correctamente el archivo KMeans.ipynb, es necesario contar con un entorno compatible con Python, como VSCode, Jupyter Notebook o Google Colab. Cualquiera de estas plataformas permite ejecutar celdas de código de manera secuencial y visualizar los resultados del análisis sin necesidad de configuraciones complejas. Además, es importante tener instaladas las librerías utilizadas en el proyecto, entre ellas: pandas, numpy, matplotlib, seaborn y scikit-learn, ya que son esenciales para el procesamiento de datos, generación de gráficos y construcción del modelo de clustering.

Una vez preparado el entorno, el proceso comienza abriendo el archivo KMeans.ipynb y ejecutando la primera sección correspondiente a las importaciones, donde se cargan todas las librerías necesarias para el análisis. Luego, se debe cargar el dataset application_.parquet, que contiene la información de los clientes utilizada para la segmentación. A continuación, se realiza una limpieza de datos que incluye la eliminación de valores nulos y duplicados, además del filtrado de outliers extremos, como ingresos improbables o registros de empleo superiores a 100 años, con el fin de asegurar que el modelo reciba datos consistentes y realistas.

Después de la limpieza, se procede a escalar las variables numéricas mediante StandardScaler, lo cual garantiza que todas las características tengan la misma escala y que ninguna domine en el proceso de formación de los clusters. Posteriormente, se ejecuta el Método del Codo (Elbow Method) para estimar un rango adecuado de valores para K, seguido del cálculo del puntaje Silhouette para evaluar la cohesión y separación entre los grupos.

Con esta información, se entrena el modelo final de K-Means utilizando k = 3, el valor óptimo identificado durante el análisis. Finalmente, se generan los gráficos correspondientes, como el gráfico del codo, la visualización del Silhouette, el conteo de clientes por cluster, el heatmap de promedios y la representación en 2D mediante PCA, los cuales permiten interpretar visualmente la estructura de los grupos formados.

3. Análisis e interpretación de resultados

Después de aplicar K-Means y evaluar diferentes valores de K mediante los métodos Elbow y Silhouette, se determinó que K = 3 era el número óptimo de clusters. Esto se debe a que la inercia deja de disminuir significativamente después de ese punto, el puntaje Silhouette presenta un valor razonablemente alto y la separación entre los grupos se aprecia clara y coherente dentro del espacio de variables analizadas.

El Cluster 0 reúne principalmente a clientes jóvenes con ingresos bajos o medios, créditos pequeños y external scores más bajos. Además, suelen presentar menor estabilidad laboral. Este es el segmento más numeroso del dataset y representa un perfil financiero básico, generalmente asociado a un mayor riesgo o una menor capacidad de pago.

Por otra parte, el Cluster 1 agrupa a clientes con ingresos elevados, créditos y gastos altos, acompañados de external scores favorables. Estos clientes presentan mayor estabilidad laboral y financiera, lo que los convierte en un segmento adecuado para productos premium y montos de crédito más elevados.

El Cluster 2 corresponde a clientes adultos con ingresos medios y un comportamiento financiero estable. Sus external scores suelen ubicarse en valores intermedios, y presentan una mayor edad y antigüedad laboral. Este grupo representa un segmento equilibrado, con estabilidad moderada y un nivel de riesgo controlado.

En conclusión, el análisis de clustering permitió identificar tres subpoblaciones bien diferenciadas dentro del conjunto de clientes. Esta segmentación facilita comprender qué tipos de clientes existen, cómo se distribuyen sus características financieras y qué grupos presentan mayor estabilidad o riesgo. Además, complementa al modelo supervisado, ya que ayuda a detectar perfiles específicos que podrían estar asociados a mayor morosidad y que no siempre son evidentes mediante un enfoque predictivo tradicional.

4. Discusión sobre la aplicabilidad del método en el proyecto final

La aplicabilidad de K-Means dentro del proyecto final de scoring crediticio es viable, aunque depende del objetivo con el que se utilice. Por un lado, su integración puede resultar beneficiosa porque permite realizar una segmentación automática basada en el comportamiento de los clientes, útil para estrategias de marketing segmentado o políticas comerciales diferenciadas. Además, complementa al modelo supervisado al revelar posibles sesgos o subgrupos ocultos que no serían detectados directamente por un modelo predictivo. También ofrece la ventaja de ser fácil de implementar en un backend futuro debido a su sencillez computacional. Sin embargo, no siempre es conveniente incorporarlo, ya que K-Means no predice riesgo directamente y requiere transformar variables categóricas antes de utilizarlas. Asimismo, no identifica causalidades, solo similitudes entre observaciones, lo que limita su interpretación en escenarios más estrictos; y además es sensible al escalado de las variables y a la presencia de outliers. Por estas razones, su uso debe evaluarse según las necesidades específicas del proyecto.

K-Means es altamente útil como complemento al proyecto, especialmente para analizar segmentos de riesgo y comportamientos poblacionales. Aporta valor comercial y analítico, es eficiente e interpretable, y funciona adecuadamente en entornos reales.

5. Conclusión General

El análisis con K-Means permitió segmentar la base de clientes en tres grupos claramente diferenciados, utilizando únicamente datos de entrenamiento y evitando data leakage, cumpliendo completamente las exigencias de la pauta.

Los segmentos obtenidos aportan información relevante para:

entender patrones de comportamiento financiero,

reforzar el modelo supervisado,

y orientar decisiones comerciales o de riesgo.

K-Means demostró ser una herramienta útil, sencilla e interpretable, viable como complemento analítico para el proyecto final.
