# 🧠 EA3 – Machine Learning: Segmentación de Clientes con K-Means

Este proyecto aplica el algoritmo **K-Means** para segmentar clientes del dataset *Home Credit*, utilizando un enfoque **no supervisado** para identificar patrones sin usar la variable objetivo.

## 📌 1. Objetivo del Proyecto
- Limpieza y selección de datos.
- Aplicación de técnicas de normalización.
- Determinación del número óptimo de clusters.
- Entrenamiento del algoritmo K-Means.
- Análisis e interpretación de los clusters formados.

---

## 2. Datos Utilizados


-----------------------------------------------------------------------------------------
READMI 
Segmentación de Clientes con K-Means
Año: 2025
Materia: Machinne Learning - 002D
Integrantes: Marcelo Mancilla - Valentina Morales 

## 1. Descripcion de la tecnica utilizada y justicaion de su eleccion
    Este proyecto fue creado con un algoritmo de aprendizaje no supervisado, donde se aplico el modelo de k-Means, cuyo objetivo es la busqueda de clusters (grupos), para estos nos basamos en la metrica de distancia.
    ° ¿Por que elegir k-Means?
    Elegimos K-Means, porque nos permite identifacr patrones que no son visibles a simple vista, como segundo lugar podemos decir que nos permitio identificar de manera automaticas los clusters dentro de los datos, por lo que el modelo tiene la capacidad de descubir por si mismo patrones y segmentos que no son evidentes a simple vista, cabe destacar que permite trabajar grandes cantidades de datos. 
    En resumen, utilizamos K-Means, ya que es un metodo de algoritmos no supervisado que se descubre por si mismo los clustters dentro de los datos, ademas es mas rapido, eficiente, permite identificar perfiles de manera clara y util para el analisis.
## 2. Intrucciones de ejecucion claras del codigo
    Para ejecutar la hoja de "KMeans.ipynb" correctamente debemos seguir los siguentes pasos;
    ojo; Abrir el archivo en VsCode, Google Colab, alguna otra que acepte los codigos de Python
    1. Instalar las librerias e importaciones que nos sirven para mostrar los resultados.
    ojo; Ir cargando los codigos en orden, como estan el la hoja de codigos
    2. Cargar y mostrar las tablas del archivo
    3. Definimos 8 variables que son las siguentes; "AMT_INCOME_TOTAL","AMT_CREDIT","AMT_ANNUITY","DAYS_BIRTH","DAYS_EMPLOYED","EXT_SOURCE_1","EXT_SOURCE_2","EXT_SOURCE_3", para posteriormente mostrar una tabla con sus datos
    4. Hcer una limpieza basica, eliminaremos los duplicados, ademas de los valores nulos.
    5. Selecionamos "AMT_INCOME_TOTA", "DAYS_EMPLOYED", esto para analizar al cliente
    6. Escalar los datos, esto quiere decir que transformamos las variables para que tengan una media de 0, y una desviacion estandar 1, esto asegura que todas las variables tengan la misma importancia, para la formacion del clusters.
    7. Metodo del Codo (Elbow Method), en este grafico se ve que prueba valores del k (1 al 10), ademas calcula la inercia (SSE)
    8. Silhouette Score, indica la calidad del clustering, por lo que mide que tan separados esta los clusters para diferentes k.
    9. Entrenar K-Means, se crea un modelo con k=3, para luego asignarle a cada cliente un cluster.
    10. Convertir days en años, facilita la lectura e interpretacion, ya que los años se ven en positivo
    11. cluster_summary, agrupa y calcula la media de cada de las 8 variables que nombramos al principio ("AMT_INCOME_TOTAL","AMT_CREDIT","AMT_ANNUITY","DAYS_BIRTH","DAYS_EMPLOYED","EXT_SOURCE_1","EXT_SOURCE_2","EXT_SOURCE_3")
    12. Grafico de barras, "Cantidad de clientes por clusters", muestra los 4 clusters y cuantos hay en cada uno
    13. Heatmap, "Promedio por clusters", muestra en un grafico de mapa de calor las medias de cada variable por clusters.
    14. pca "Clusters visualizados en 2D (PCA)", se muestra visualizado como se reducen los datos en 2 dimensiones
    15. Visualizacion de los clusters, por cada uno se ven las 8 variables, esto sirve para interpretar como se caracteriza cada clusters
    16. "Targert", calcula el promedio de cada cluster
## 3. Analisis e interpretacion de resultados
    Como resultado, podemos decir que al aplicar K-Means se determinaron que en el modelo final se detectaron 3 cluster, con 8 variables cada uno, dondde se interpretaron los grupos de clientes, cabe destacar que para llegar a la cifra de 3 cluster utilizamos el Metodo del Codo(Elbow Method), donde se mostro que k=3, mejora en la inercia dejaba de ser significattivo, ademas de utilizar el Silhoutte Score, donde se confirmo la separacion y cohesion de los grupos es mayor al usar 3 clusters. 
    A continuacion analizaremos cada uno de los clusters;
    - Clusters 0; podemos decir que represneta a clientes jovenes, con ingresos bajo-medios, con creditos pequeños y menores, esto indica que el external scores mas bajos, en resumen podemos decir que este cluster es un segmento grande, pero de clientes jovenes con menor poder adquisitivo, ademas de tener menor estabilidad financiera
    - Clusters 1; representa a clientes con ingresos alto, con gastos altos, cuentan con alto poder adquisitivo, alto montos de creditos y su external scores mejores, podemos resumir con que son clientes de alto valor economico, con una capacidad de credito mayor, ademas de tener buen perfil en general, por lo que se pueden convertir en premium
    - Clusters 2; represneta a los ingresos medios, con gastos estables,con un buen comportamiento, este es el intermedio de los dos anteriores, estos representan a personas mayores, cuentan con mejores indicadores de solvencia, en resumen tienen buen historial de creditos, pero no cuentan con ingresos tan altos como el clusters 1.
    En conclusion general, el modelo K-Menas con un k=3, logro seprar correctamente a los clientes en grupos coherentes, esto permite entender mejor los patrones de riesgo, ademas de personalizar las desiciones comerciales.
## 4. Discusion sobre si el metodo aplicado podria o no incorporarse al proyecto final, explicando las razones 
    El metodo que nostros aplicamos fue el K-Means, este si podria incorporarse al proyecto final, por las siguentes razones;
    - Facil de integrar; es un modelo eficiente y simple de inplementar dentro de un backend en un futuro
    - Segmento util; el modelo divide a los clientes en grupos naturales, esto es util, ya que para sistemas que buscan personalizar sus recomendaciones hacia sus clientes, ademas gestiona a los clientes o analiza sus comportamientos
    - Valor al negocio; como ya lo explique en puntos anteriores, este permite que el negocio, tenga ofertas, servicios o productos, mas personalizados segun el cliente.
    Tambien daremos las explicaciones de porque no seria factible ocupar el modelo de K-Means;
    - este modelo no predice, si se necesitara prediciones futuras no lo podria hacer
    - se basa en datos categoricos, por lo que no es convatible con los numeros
    - este modelo solo agrupa, por lo tanto no podria interpretar casualidades.
    Como conclusion final, el modelo de K-Means es una modelo efectivo para segmentar a los clientes, ademas de descubir sus patrones de comportamientso, con la elecion de 3 clusters, esta fue validada matematicamente, los perfiles aportan una comprension profunda en el comportamiento del cliente, cabe destacar que el metodo es viable para una implementacion futura en el proyecto final, con su capacidad de segmentacion, un aporte analitico y facil de uso.
