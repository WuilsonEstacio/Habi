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
- **Montos (`transaction_amount`)**  



