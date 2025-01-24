# Habi
prueba_habi

Este Documento describe el proceso para solucion de la prueba de Habi **extracion**, **Exploracion** , *Resultados exploracion**, **Modelo**, **Dificultades**, **Concluciones**.

---

## Tabla de Contenido
1. [Introducción](#introducción)  
2. [Objetivo](#objetivo)  
3. [Alcance y Definiciones](#alcance-y-definiciones)  
4. [Exploración y Evaluación de Datos (EDA)](#exploración-y-evaluación-de-datos-eda)  
   - [Calidad de Datos](#calidad-de-datos)  
   - [Estadísticos Descriptivos](#estadísticos-descriptivos)
5. [Resultados](#resultados)
---

## Introducción
En el marco de esta prueba tecnica se facilitan los link de acceso donde se debe tomar la informacion y dar solucion a los 6 puntos planteados, los cuales se resumen en crear un pipeline que extraiga la informacion de las fuentes y se ejecute sin necesidad de que quede en el disco. calcular cuántas ofertas inmobiliarias existen en Bogotá por UPL y permitir ver cuántas ofertas de inmuebles existen por UPL. luego hacer una i de Moran para saber las UPLs HH, HL, LH y LL según el modelo para el valor por m2 de los inmuebles por UPL como paso siguiente hacer el modelo de predicción de precios de su preferencia para valorar los inmuebles proporcionados y presentar el MAPE y RMSE del resultado.

El contenido de esta carpeta esta compuesto de la siguiente forma:
1. Data, alli descargara algunos archivos que llega a necesitar.
2. Imagenes: esta contiene las imagenes generadas por el codigo.
3. habi: contiene archivos de la realizacion de algunas pruebas y graficas realizadas con Qgis
4. Scrip este contien el scrip que contiene el desarrollo de los puntos planteados, sus graficas y notas. el codigo tiene como nombre Prueba_Data_Science_solver.ipynb
   
---
## Objetivo
Generar un pipeline de descarga y ejecucion automatico.
Identificar cuantas oferttas inmoviliares existen por upl en Bogota, y graficar.
Ver el indice de mora y lisa para Bogota por precio y ver si hay correlacion espacial.
Generar un modelo para predecir los precios de las viviendas.

---
## Alcance y Definiciones
- **EPSG** las EPSG  4686 es la proyectada y la 4326 es geografica y la 3116 esta en metros

---

## Exploración y Evaluación de Datos (EDA)
Durante esta fase, se realizaron **descriptivos** y **validaciones** de calidad para comprender el comportamiento de los datos.

### Muestreo de los Datos
Se trabajó para los primeros puntos se trabajo con el total de los datos pero por capacidad de procesamiento y tiempo de ejecucion 
en la parte del eda solo se trabajo con una muestra para la prueba y para el resultado del indice de moran se trabajo solo con el codigo upl 18. 

### Calidad de Datos
1. **Valores Nulos / Faltantes**  
   - Si identificaron valores nulos a nivel de registro. a demas de identificacion de duplicados en las variables
   - algunos se corriguieron otras variables se omitieron dado que no trabajariamos con ellas.

3. **Consistencia en fechas**
   - Rango de fechas plausibles (Fecha mínima: 2020-04-14, Fecha máxima: 2022-07-16)

### Estadísticos Descriptivos
- **Se encintraron las siguientes distribuciones para la cuidad de bogota, referentes a inmuebles**
![Estadísticos Descriptivos](./imagenes/bano_desc.png "Distribución de Tipos de cantidad de baños en las casa de Bogotá")
![Estadísticos Descriptivos](./imagenes/inmuebles_desc.png "Distribución de Tipos de Inmuebles en Bogotá")
![Estadísticos Descriptivos](./imagenes/negocios_desc.png "Distribución de Tipos de negocio en Bogotá")

- Esto nos genera una idea de como estan las habitas en bogota, donde el 80% de las habitas tienen entre 2 y 3 baños.
- El 70.4%  de los inmuebles en Bogota en este dataset estan para la venta y el 29.6% estan para arrendar. y el 83% de estos inmuebles son apartamento.
- 
![Estadísticos Descriptivos](./imagenes/tipo_inmueble_tipo_negocio.png "Relación entre Tipo de Inmueble y Tipo de Negocio")

- Para antes de generar el modelo se tuvo que mirar como es la correlacion dde las variables respecto a nuestra variable target en este caso precio, su correlacion con spearman es la de la siguiente grafica, donde se debieron omitir en un principio las de muy alta correlacion y de correlacion casi nula
  
![Estadísticos Descriptivos](./imagenes/correlacion_precio.png "Correlacion de sperman de las variables con respecto al precio")

---

## Resultados
Acontinuacion se muestra un resumen visual de algunos de los puntos de interes.
- Dado la capacidad de procesamiento se trabajo con la UPL18, Donde el Moran's I observado es: 0.026779042642575197 y el p-value aproximado: 0.001.
- Dado los resultados para la UPL18 vemos el valor observado del indice de moran indica una autocorrelacion espacial dabil, lo que significa que no hay una fuerte tendencia a quevalores similares(altos o bajos) esten agrupados espacial,emte, adicionalmente, el p value  indica significancia estadistica  del indice de moran, en otras palabras indica que hay evidencia para sugerir que existe algun tipo de patron espacial en los datos.

![Resultados](./imagenes/imagen_moran_c.jpg "Grafica de correlacion de moran-lisa para la UPL18")


- A continuacion se muestra la Frecuencia_upls_bogota en la cual tenemos como es su distribuciones de frecuencia y vemos que la UPL25 es la mas frecuente con mas de 104775 valoes en la ciudad de bogota.

![Resultados](./imagenes/Frecuencia_upls_bogota.jpg "Frecuencia de valores en UPLs en Bogotá")

- Aqui tenemos un mapa de calor  para esa la cantidad de ofertas en bogota.

![Resultados](./imagenes/Mapa_calor_oferte_bogota.jpg "Mapa de Calor de Cantidad Oferta en Bogotá")

