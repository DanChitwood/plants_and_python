# 4.1 Head y tail

## Cómo evaluar rápidamente las propiedades del marco de datos, usando `head` y `tail`
_____

***Mira este video de 2:25 a 4:12***

Para español, haga click en configuración, seleccione "español" debajo de los subtítulos.

Traducción por Guillermo Rodríguez Guerrero (UNAM ENES León, México).


```python
# Para reproducir el siguiente tutorial, presiona shift + enter

from IPython.display import YouTubeVideo
from datetime import timedelta
start=int(timedelta(hours=0, minutes=2, seconds=25).total_seconds())
end=int(timedelta(hours=0, minutes=4, seconds=12).total_seconds())

YouTubeVideo("jEQRU55x0e4",start=start,end=end,width=640,height=360)
```





<iframe
    width="640"
    height="360"
    src="https://www.youtube.com/embed/jEQRU55x0e4?start=145&end=252"
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

Ahora veamos cómo mirar nuestro marco de datos usando "head" y "tail".

Por lo tanto, es importante saber con qué se está trabajando 
para ver el marco de datos y "head" y "tail" nos permite hacer eso. Así que recuerda que los datos se almacenan en el objeto data y usamos ".head" y lo que veremos es una vista previa de las primeras cinco filas y también obtendremos los nombres de las columnas.


```python
# Es importante saber con qué estás trabajando
# para "ver" el marco de datos
# .head() muestra las primeras filas y los nombres de las columnas

data.head()
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
      <th>date</th>
      <th>running_date</th>
      <th>month</th>
      <th>year</th>
      <th>CO2ppm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>8/13/17</td>
      <td>1</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>8/14/17</td>
      <td>2</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>8/15/17</td>
      <td>3</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8/16/17</td>
      <td>4</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8/17/17</td>
      <td>5</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.2</td>
    </tr>
  </tbody>
</table>
</div>



También podemos usar "tail". Y "tail", si "head" está al principio, entonces "tail" es el final. Y puedes ver que obtenemos las últimas filas de nuestro conjunto de datos. "tail" es muy útil para ver solo cuántas filas tienes en total. Recuerda que comenzamos con cero, entonces tenemos 714 filas o puntos de datos en este conjunto de datos.


```python
# .tail() muestra las últimas filas

data.tail()
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
      <th>date</th>
      <th>running_date</th>
      <th>month</th>
      <th>year</th>
      <th>CO2ppm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>709</th>
      <td>7/23/19</td>
      <td>710</td>
      <td>jul</td>
      <td>2019</td>
      <td>410.87</td>
    </tr>
    <tr>
      <th>710</th>
      <td>7/24/19</td>
      <td>711</td>
      <td>jul</td>
      <td>2019</td>
      <td>410.87</td>
    </tr>
    <tr>
      <th>711</th>
      <td>7/25/19</td>
      <td>712</td>
      <td>jul</td>
      <td>2019</td>
      <td>410.87</td>
    </tr>
    <tr>
      <th>712</th>
      <td>7/26/19</td>
      <td>713</td>
      <td>jul</td>
      <td>2019</td>
      <td>410.87</td>
    </tr>
    <tr>
      <th>713</th>
      <td>7/27/19</td>
      <td>714</td>
      <td>jul</td>
      <td>2019</td>
      <td>410.87</td>
    </tr>
  </tbody>
</table>
</div>



"Describe" es una función muy útil que te devuelve estadísticas resumidas para tus variables continuas. Entonces, si usamos "describe" en nuestros datos, lo que obtenemos es la fecha de ejecución, que fue solo desde el día uno hasta el 714, un número que aumenta para realizar un seguimiento del día; el año se incluye como una variable continua, aunque no queremos que sea una variable continua; y partes de CO2 por millón, es, por supuesto, una variable continua. Obtenemos cuánto de cada uno tenemos. Tenemos 714 de cada uno. Obtenemos la media de cada uno; la desviación estándar; el mínimo; los cuartiles en el 25,
50 y 75, cuartiles; y el valor máximo también. 


```python
# .describe() es muy útil, muestra estadísticas resumidas
# proporciona estadísticas para variables continuas

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
      <th>year</th>
      <th>CO2ppm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>714.000000</td>
      <td>714.000000</td>
      <td>714.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>357.500000</td>
      <td>2018.093838</td>
      <td>408.977059</td>
    </tr>
    <tr>
      <th>std</th>
      <td>206.258333</td>
      <td>0.693299</td>
      <td>3.189098</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>2017.000000</td>
      <td>402.760000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>179.250000</td>
      <td>2018.000000</td>
      <td>406.530000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>357.500000</td>
      <td>2018.000000</td>
      <td>409.010000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>535.750000</td>
      <td>2019.000000</td>
      <td>411.450000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>714.000000</td>
      <td>2019.000000</td>
      <td>415.390000</td>
    </tr>
  </tbody>
</table>
</div>



Así es como se lee en un marco de datos,
cómo mirar rápidamente el marco de datos y obtener 
estadísticas resumidas de las variables continuas.
