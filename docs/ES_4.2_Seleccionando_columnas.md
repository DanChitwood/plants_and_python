# 4.2 Seleccionando columnas

## Cómo seleccionar columnas de un marco de datos
_____

***Mira este video de 4:12 a 6:01***

Para español, haga click en configuración, seleccione "español" debajo de los subtítulos.

Traducción por Guillermo Rodríguez Guerrero (UNAM ENES León, México).


```python
# Para reproducir el siguiente tutorial, presiona shift + enter

from IPython.display import YouTubeVideo
from datetime import timedelta
start=int(timedelta(hours=0, minutes=4, seconds=12).total_seconds())
end=int(timedelta(hours=0, minutes=6, seconds=1).total_seconds())

YouTubeVideo("jEQRU55x0e4",start=start,end=end,width=640,height=360)
```





<iframe
    width="640"
    height="360"
    src="https://www.youtube.com/embed/jEQRU55x0e4?start=252&end=361"
    frameborder="0"
    allowfullscreen
></iframe>




***La siguiente es una transcripción del video.***

> 💡 ***Recuerde:*** Importe `pandas` y lea el conjunto de datos a continuación para completar esta lección


```python
# Importe pandas

import pandas as pd
```


```python
# Decargue el conunto de datos del
# Jupyter Book para leer localmente o
# leer desde GitHub, a continuación:

data = pd.read_csv('https://raw.githubusercontent.com/DanChitwood/PlantsAndPython/master/co2_mlo_weekly.csv')
```

Aprendamos a seleccionar columnas específicas del marco de datos.

Si recuerdas, solo en el ejemplo anterior, ese año se trató como una variable continua. Los datos que lees tienen los años: datos de los años 2017, 2018 y 2019. Pero no queremos que se traten como números, queremos que sean tratados como una variable categórica, como si fueran el año "A", el año "B" o el año "C". Así que intentemos cambiar nuestra columna "year" en una variable categórica.

Pero para hacer eso necesitamos saber cómo hacer referencia a columnas específicasen pandas, y esto es extremadamente fácil. Esta es una de las mejores cosas de usar un marco de datos es 
que simplemente puedes referirte a las columnas por su nombre, en lugar de un número de índice. 

Entonces, si queremos la columna "year", todo lo que hacemos es para nuestros datos de marco de datos, tenemos corchetes y simplemente nos referimos al año como una cadena entre comillas. Si queremos poner año a una variable categórica, usamos la función "astype()" para convertirla en una cadena, lo que la convierte en una variable categórica. Entonces decimos para la columna del año, refiriéndonos a ella como un string queremos convertirlo astype() en un string, y volvemos a establecer la columna del año en un string que hace a sí mismo.


```python
# En el ejemplo anterior, el 'year' era continuo.
# pero queremos que el año sea categórico

# ¿Cómo nos referimos a una columna específica?

# Simplemente use el nombre de la columna entre corchetes, como una cadena!

# Después de obtener la columna 'year', simplemente use .astype () para cambiar a cadena

data['year'] = data['year'].astype(str)
```

Así que verifiquemos que tuvimos éxito y ahora puedes ver cuando usamos "describe" que ya no se ve aquí, porque no puede tomar una media, un mínimo o un máximo de una variable categórica,
ahora solo tenemos fechas de ejecución y partes de CO2 por 
millón, pero esto fue para mostrarte que puedes acceder a una columna específica simplemente refiriéndose a ella como un string entre corchetes para un marco de datos en pandas.


```python
# Comprobemos con .describe () ahora si 'year' es categórico

data.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>running_date</th>
      <th>CO2ppm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>714.000000</td>
      <td>714.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>357.500000</td>
      <td>408.977059</td>
    </tr>
    <tr>
      <th>std</th>
      <td>206.258333</td>
      <td>3.189098</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>402.760000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>179.250000</td>
      <td>406.530000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>357.500000</td>
      <td>409.010000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>535.750000</td>
      <td>411.450000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>714.000000</td>
      <td>415.390000</td>
    </tr>
  </tbody>
</table>
</div>


