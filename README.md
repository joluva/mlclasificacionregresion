# Machine Learning Clasificación y Regresión
Repo MachineLearning Clasificacion y Regrasion - APIS

## Actividad 1

### Situación 
¡Felicidades! Recientemente, nos han contratado como data scientist junior para la empresa Trump and Co. Matriz latinoamericana de Trump International, cuyo fondo de inversiones se dedicaba a los bienes raíces (real state). Nuestro nuevo jefe desea implementar un modelo de machine learning basado en regresión lineal que permita predecir el precio de las propiedades. 
Para diseñar el modelo de machine learning, se ha dispuesto la estrategia de modelar un modelo Dummy o de prueba a partir de un caso internacional conocido como Ames Housing Dataset.
El conjunto de datos Ames fue introducido por el profesor Dean De Cok en 2011 como una variante del caso Boston del año 1978.

### Consignas
El primer procedimiento que realizaremos corresponde a descargar el dataset, el cual podrá estar en formato Excel o CSV.  
A continuación, debemos reconocer las librerías necesarias para llevar a cabo la transformación de los datos en un data frame. También será necesario trabajar con un conjunto de pruebas equivalente al 20 % del total de los datos.
Es de suma importancia reconocer el número total de observaciones que cuentan con datos perdidos en el data set y con los datos nulos.
La primera parte del estudio previo estará compuesto por la matriz de correlación con las variables con una correlación superior al 60 % (equivalente a 0.60).

___

### Data Set utilizdo, se encuenta en Kaggle HamesHousing.csv
Contiene información de RealState

___

### Librerias utilizadas
* pandas
* numpy
* seaborn
* matplotlib
* Scikit-learn

___

### Información adicional. 
#### Que significa este paso, por qué es importante en un proyecto de regresión lineal para precios inmobiliarios (como el que estamos armando para Trump and Co.), y cómo identificamos cuáles observaciones (es decir, qué filas específicas) tienen datos perdidos o nulos.

##### 1. ¿Qué son los “datos perdidos” en este contexto?
* En Pandas, un valor perdido se representa como:

    * NaN (Not a Number) → valor numérico nulo.
    * None o NaT (para fechas).

En el Ames Housing Dataset (2.930 observaciones × 82 columnas), los valores nulos NO son siempre errores.
Dean De Cock diseñó el dataset de forma que muchos “NA” tienen significado semántico muy útil para predecir el precio:

 | Columna | Qué significa NA | Ejemplo de interpretación inmobiliaria |
|---------|----------------|------------------------------------------|
| PoolQC | No tiene piscina | La propiedad no tiene piscina de lujo |
| MiscFeature | No tiene característica miscelánea | No tiene ascensor, pista de tenis, etc. |
| Alley | No tiene callejón | No tiene acceso por callejón privado |
| Fence | No tiene cerca | No tiene cerco perimetral |
| FireplaceQu | No tiene chimenea | Propiedad sin chimenea |
| GarageType / GarageFinish / GarageQual / etc. | No tiene garaje | La casa no incluye garaje |
| LotFrontage | Frente de lote desconocido | Dato realmente perdido (este sí es “missing”) |


Importante para real estate: estos “NA” son información valiosa. Una casa sin piscina suele valer menos que una con piscina. Por eso no debemos eliminar las filas; debemos tratarlos como una categoría (“Sin piscina”, “Sin garaje”, etc.).

___

## Actividad 2

### Situación
Sin duda es un buen comienzo el procesamiento de datos realizados al dataset “Ames Housing Dataset”. Durante la mañana del próximo lunes serán revisados los resultados iniciales del procesamiento de datos que usted realizó. En la junta se precisa avanzar con el modelo de regresión lineal. 
Para avanzar en esta tarea, se pide cuantificar los datos nan ordenando de mayor a menor las variables que contienen valores.
Luego se pide crear una función y ejecutarla de modo de eliminar los datos de las columnas detectadas.
Identificados los datos nan y null, se requiere eliminar dicha data desde el data frame.
Con el data frame limpio se pide dividir el conjunto de datos df_train y df_test con un test size 0.2 y un random state 42.
Cargar el modelo de regresión lineal. Luego, usando las variables X_train e Y_train, procediendo a calcular el precio de las variables. Se requiere print con el valor de la predicción y el valor real de las viviendas.
Finalmente, se pide estimar el valor del modelo de regresión mediante MSE.

### Consigna
Se solicita diseñar un modelo de regresión lineal usando la variable objetivo SalePrice.

___


### Data Set utilizdo, se encuenta en Kaggle HamesHousing.csv
Contiene información de RealState

___

### Librerias utilizadas
* pandas 
* numpy 
* sklearn.model_selection import train_test_split
* sklearn.linear_model import LinearRegression
* sklearn.metrics import mean_squared_error

___

### Notas importantes
* Si el dataset tiene muchas columnas categóricas, usa pd.get_dummies() para convertir.

* Si hay valores infinitos o muy extremos, considera aplicar np.log1p a SalePrice.

* Asegúrate de que X_train e y_train sean del mismo largo.

* El random_state=42 garantiza reproducibilidad.