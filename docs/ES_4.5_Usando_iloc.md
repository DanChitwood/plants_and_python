# 4.5 Usando iloc

## Cómo usar `iloc` para aislar datos dentro de un marco de datos (filas primero, columnas segundo, inicio:final y corchetes)
______

***Mira este video de 12:06 a 16:25***

Para español, haga click en configuración, seleccione "español" debajo de los subtítulos.

Traducción por Guillermo Rodríguez Guerrero (UNAM ENES León, México).


```python
# Para reproducir el siguiente tutorial, presiona shift + enter

from IPython.display import YouTubeVideo
from datetime import timedelta
start=int(timedelta(hours=0, minutes=12, seconds=6).total_seconds())
end=int(timedelta(hours=0, minutes=16, seconds=25).total_seconds())

YouTubeVideo("jEQRU55x0e4",start=start,end=end,width=640,height=360)
```





<iframe
    width="640"
    height="360"
    src="https://www.youtube.com/embed/jEQRU55x0e4?start=726&end=985"
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

A continuación, veamos otra forma de encontrar datos específicos. y esto se llama función "iloc". Y esto usará filas y columnas para encontrar los datos que quieres. Es algo así como Excel, piensa en qué filas y columnas deseas aislar de los datos. Lo puedes hacer, tanto para las filas como para las columnas, puedes usar la indexación con la notación de dos puntos de inicio y final que aprendiste antes. 

Así que repasemos de nuevo como se ven nuestros datos, recuerda que usamos "head", que solo trae de vuelta las primeras cinco columnas, pero lo más importante es que te da los nombres de las columnas. Y podemos ver que la primera columna es "date", la segunda columna es "running_date", la tercera columna es "month", la cuarta es "year", y la quinta es "CO2ppm".


```python
# También podemos acceder a filas y columnas específicas
# usando indexación con .iloc ()

# Veamos los datos nuevamente usando .head ()

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



Entonces, todo lo que necesita saber sobre "iloc" es que la primera posición son las filas, la segunda posición son las columnas, y puedes usar la indexación para filas y columnas. 

Entonces, si solo usamos "data.iloc" y solo ingresamosun número, es la ranura de las filas. Recuerda, la indexación comienza en cero, por lo que esto debería devolvernos solo la primera fila de data.

Y tú puedes ver que esto es 13 de agosto de 2017, fecha de ejecución 1 , mes agosto, año 2017, y partes por millón 405.2, que es la primera fila de data. Entonces, las filas y 
luego el índice nos dan la primera fila de data.


```python
# La primera posición en .iloc son las filas
# La segunda posición en .iloc son las columnas
# Usamos indexación y dos puntos start:end
# para hacer referencia a qué filas y columnas queremos

# La indexación comienza en 0, por lo que volvemos a la primera fila

data.iloc[0]
```




    date            8/13/17
    running_date          1
    month               aug
    year               2017
    CO2ppm            405.2
    Name: 0, dtype: object



Recuerda, uno negativo en la indexación es una forma de obtener el último elemento y, por lo tanto, si solo hacemos uno negativo
de nuevo, posición de la fila, y volvemos a la última fila. Y puedes ver que es la última fila porque tiene la fecha de ejecución de 714.


```python
# -1 con indexación es el último elemento
# devuelve la última fila

data.iloc[-1]
```




    date            7/27/19
    running_date        714
    month               jul
    year               2019
    CO2ppm           410.87
    Name: 713, dtype: object



Podemos hacer referencia a filas y columnas, por lo que podríamos decir la última fila, y recuerda, si solo ponemos dos puntos, que deberían tener el inicio y el final, pero no ponemos cualquier número, solo vamos a obtener todos los valores, por lo que esta será la última fila pero todas las columnas. Y de 
hecho eso es lo que obtenemos: la última fila, 714, pero todas las columnas, lo que equivale a poner un 1 negativo. Pero también funciona de esta manera porque formalmente hablando que queremos todas las columnas.


```python
# Podemos hacer referencia a la última fila y a todas las columnas.

data.iloc[-1, :] # start:end, but : refers to all columns
```




    date            7/27/19
    running_date        714
    month               jul
    year               2019
    CO2ppm           410.87
    Name: 713, dtype: object



En este caso, con solo dos puntos vacíos para las filas, estamos diciendo que queremos todas las filas, pero solo queremos la primera columna, la columna de índice cero, recuerda que es la fecha, así que obtenemos todas las fechas porque pedimos todas las filas de solo la primera columna.


```python
# Aquí ":" se refiere a todas las filas.
# para la primera columna referida con 0

data.iloc[:,0]
```




    0      8/13/17
    1      8/14/17
    2      8/15/17
    3      8/16/17
    4      8/17/17
    5      8/18/17
    6      8/19/17
    7      8/20/17
    8      8/21/17
    9      8/22/17
    10     8/23/17
    11     8/24/17
    12     8/25/17
    13     8/26/17
    14     8/27/17
    15     8/28/17
    16     8/29/17
    17     8/30/17
    18     8/31/17
    19      9/1/17
    20      9/2/17
    21      9/3/17
    22      9/4/17
    23      9/5/17
    24      9/6/17
    25      9/7/17
    26      9/8/17
    27      9/9/17
    28     9/10/17
    29     9/11/17
            ...   
    684    6/28/19
    685    6/29/19
    686    6/30/19
    687     7/1/19
    688     7/2/19
    689     7/3/19
    690     7/4/19
    691     7/5/19
    692     7/6/19
    693     7/7/19
    694     7/8/19
    695     7/9/19
    696    7/10/19
    697    7/11/19
    698    7/12/19
    699    7/13/19
    700    7/14/19
    701    7/15/19
    702    7/16/19
    703    7/17/19
    704    7/18/19
    705    7/19/19
    706    7/20/19
    707    7/21/19
    708    7/22/19
    709    7/23/19
    710    7/24/19
    711    7/25/19
    712    7/26/19
    713    7/27/19
    Name: date, Length: 714, dtype: object



También podríamos obtener todas las filas para la segunda columna, recuerda que la segunda columna es la fecha de ejecución, por lo que es de uno a 714.


```python
# También podríamos obtener todas las filas
# y la segunda columna, en el índice 1

data.iloc[:,1]
```




    0        1
    1        2
    2        3
    3        4
    4        5
    5        6
    6        7
    7        8
    8        9
    9       10
    10      11
    11      12
    12      13
    13      14
    14      15
    15      16
    16      17
    17      18
    18      19
    19      20
    20      21
    21      22
    22      23
    23      24
    24      25
    25      26
    26      27
    27      28
    28      29
    29      30
          ... 
    684    685
    685    686
    686    687
    687    688
    688    689
    689    690
    690    691
    691    692
    692    693
    693    694
    694    695
    695    696
    696    697
    697    698
    698    699
    699    700
    700    701
    701    702
    702    703
    703    704
    704    705
    705    706
    706    707
    707    708
    708    709
    709    710
    710    711
    711    712
    712    713
    713    714
    Name: running_date, Length: 714, dtype: int64



Recuerda, puedes usar la indexación tanto para las filas como para las columnas. La indexación es inclusiva del inicio pero hasta el final y sin incluirlo. Entonces en este caso estamos diciendo que queremos las flas dos y tres porque vamos a subir pero sin incluir cuatro, así que estas son las filas dos y tres
para columnas desde dos hasta el final, que sería la tercera columna hasta el final.

Como puedes ver obtenemos las filas dos y tres que incluyen el inicio también y sin incluir cuatro, las filas dos y tres, y
obtenemos la segunda posición de índice de las columnas, que es la tercera columna hasta el final.


```python
# La indexación se puede utilizar tanto 
# para las filas como para las columnas

data.iloc[2:4, 2:] # indexing inclusive of start but not the end
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
      <th>month</th>
      <th>year</th>
      <th>CO2ppm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>aug</td>
      <td>2017</td>
      <td>405.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>aug</td>
      <td>2017</td>
      <td>405.2</td>
    </tr>
  </tbody>
</table>
</div>



Puedes usar corchetes separados por comas para obtener filasmuy específicas en columnas muy específicas. Y que si quisieras
posiciones de índice 0, 3, 5 y 7 para filas y posiciones de columna 0, 2 y 4? Y luego puedes ver que eso es exactamente lo que obtenemos:las filas indexadas por esos números aleatorios
y luego la primera, tercera y quinta columnas, porque recuerda que la indexación comienza en cero.


```python
# Los corchetes entre corchetes se pueden utilizar 
# para hacer referencia a filas y columnas específicas

data.iloc[[0,3,5,7],[0,2,4]]
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
      <th>month</th>
      <th>CO2ppm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>8/13/17</td>
      <td>aug</td>
      <td>405.20</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8/16/17</td>
      <td>aug</td>
      <td>405.20</td>
    </tr>
    <tr>
      <th>5</th>
      <td>8/18/17</td>
      <td>aug</td>
      <td>405.20</td>
    </tr>
    <tr>
      <th>7</th>
      <td>8/20/17</td>
      <td>aug</td>
      <td>404.54</td>
    </tr>
  </tbody>
</table>
</div>



Entonces, iloc es una forma muy específica de obtener
datos muy específicos por fila o por columna.
