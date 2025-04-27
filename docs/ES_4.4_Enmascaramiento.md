# 4.4 Enmascaramiento

## Cómo enmascarar datos (una declaración booleana para pescar los datos que desea, corchetes después de un marco de datos
____

***Mira este video de 8:06 a 12:06***

Para español, haga click en configuración, seleccione "español" debajo de los subtítulos.

Traducción por Guillermo Rodríguez Guerrero (UNAM ENES León, México).


```python
# Para reproducir el siguiente tutorial, presiona shift + enter

from IPython.display import YouTubeVideo
from datetime import timedelta
start=int(timedelta(hours=0, minutes=8, seconds=6).total_seconds())
end=int(timedelta(hours=0, minutes=12, seconds=6).total_seconds())

YouTubeVideo("jEQRU55x0e4",start=start,end=end,width=640,height=360)
```





<iframe
    width="640"
    height="360"
    src="https://www.youtube.com/embed/jEQRU55x0e4?start=486&end=726"
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

A continuación, hablaremos de algo llamado enmascaramiento. El enmascaramiento es muy importante y es una forma de encontrar datos específicos que cumplen un criterio y es una declaración booleana; recuerda, una declaración booleana es algo que solo se puede evaluar como Verdadero o Falso, para encontrar todos los datos en su marco de datos que sean verdaderos con respecto a la declaración booleana.

Así que esto es lo que hace el enmascaramiento: nos da datos específicos y, como dije, es muy simple, una máscara es solo una declaración booleana.

Entonces decimos que la máscara es igual a y luego tenemos una declaración booleana. Entonces, para los datos en la columna del mes, los meses, la declaración booleana es que es igual a agosto. Usamos un doble igual aquí porque recuerda, cuando usamos Python, puede tener menor o igual a, mayor o igual a, pero igual a igual es verdaderamente igual. Entonces, la declaración booleana es elmes de agosto, Verdadero o Falso, esa es la máscara, y estamos estableciendo esta declaración booleana 
igual a la máscara. 

Entonces presionamos shift + enter y luego podemos ver qué es la máscara.


```python
# ¿Cómo obtenemos datos específicos?
# ¿Qué pasa si queremos todos los puntos de datos solo del mes de agosto?
# ¡Creamos una máscara!
# Una máscara es una declaración booleana donde los datos que desea son TRUE

mask = data['month']=='aug'
```

Y lo que ves es la máscara, es que devuelve las filas del
marco de datos que cumplen los criterios. Entonces, este es 
un marco de datos grande, por lo que comienza desde el principio
luego se rompe y luego llega hasta elfinal. Si recuerdas, el mes de agosto fue el primer valor de data. Así que puedes ver que estasfechas de agosto, eran las que estaban en la parte superior de del marco de datos, se evalúan como Verdadero. Pero luego 
evalúan como Falso cuando el mes no es agosto.


```python
# La máscara devuelve qué filas se evalúan como TRUE para la declaración booleana

mask
```




    0       True
    1       True
    2       True
    3       True
    4       True
    5       True
    6       True
    7       True
    8       True
    9       True
    10      True
    11      True
    12      True
    13      True
    14      True
    15      True
    16      True
    17      True
    18      True
    19     False
    20     False
    21     False
    22     False
    23     False
    24     False
    25     False
    26     False
    27     False
    28     False
    29     False
           ...  
    684    False
    685    False
    686    False
    687    False
    688    False
    689    False
    690    False
    691    False
    692    False
    693    False
    694    False
    695    False
    696    False
    697    False
    698    False
    699    False
    700    False
    701    False
    702    False
    703    False
    704    False
    705    False
    706    False
    707    False
    708    False
    709    False
    710    False
    711    False
    712    False
    713    False
    Name: month, Length: 714, dtype: bool



Podemos obtener todos los datos. Así que esto es todo lo que hace una máscara: está regresando para las filas que son Verdadero y Falso, pero si coloca la máscara dentro de los corchetes del marco de datos lo que obtienes es el marco de datos completo, esas filas del marco de datos que se evalúan como Verdadero.

Entonces, por ejemplo, aquí puedes ver lo que obtenemos son solo datos que son el mes de agosto. Estas fueron las únicas filas que cumplieron con la declaración booleana de ser Verdadero
que eran agostos.

Así que eso es todo lo que es la máscara: recuerda que una máscara es solo una declaración booleana y ponemos la máscara entre paréntesis del marco de datos para devolver esas filas que se evalúan como Verdadero para la declaración booleana.


```python
# Si colocamos la máscara dentro de los corchetes del marco de datos
# luego se devuelven las filas donde la declaración es True

data[mask]
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
      <td>405.20</td>
    </tr>
    <tr>
      <th>1</th>
      <td>8/14/17</td>
      <td>2</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>8/15/17</td>
      <td>3</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.20</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8/16/17</td>
      <td>4</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.20</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8/17/17</td>
      <td>5</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.20</td>
    </tr>
    <tr>
      <th>5</th>
      <td>8/18/17</td>
      <td>6</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.20</td>
    </tr>
    <tr>
      <th>6</th>
      <td>8/19/17</td>
      <td>7</td>
      <td>aug</td>
      <td>2017</td>
      <td>405.20</td>
    </tr>
    <tr>
      <th>7</th>
      <td>8/20/17</td>
      <td>8</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.54</td>
    </tr>
    <tr>
      <th>8</th>
      <td>8/21/17</td>
      <td>9</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.54</td>
    </tr>
    <tr>
      <th>9</th>
      <td>8/22/17</td>
      <td>10</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.54</td>
    </tr>
    <tr>
      <th>10</th>
      <td>8/23/17</td>
      <td>11</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.54</td>
    </tr>
    <tr>
      <th>11</th>
      <td>8/24/17</td>
      <td>12</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.54</td>
    </tr>
    <tr>
      <th>12</th>
      <td>8/25/17</td>
      <td>13</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.54</td>
    </tr>
    <tr>
      <th>13</th>
      <td>8/26/17</td>
      <td>14</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.54</td>
    </tr>
    <tr>
      <th>14</th>
      <td>8/27/17</td>
      <td>15</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.23</td>
    </tr>
    <tr>
      <th>15</th>
      <td>8/28/17</td>
      <td>16</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.23</td>
    </tr>
    <tr>
      <th>16</th>
      <td>8/29/17</td>
      <td>17</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.23</td>
    </tr>
    <tr>
      <th>17</th>
      <td>8/30/17</td>
      <td>18</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.23</td>
    </tr>
    <tr>
      <th>18</th>
      <td>8/31/17</td>
      <td>19</td>
      <td>aug</td>
      <td>2017</td>
      <td>404.23</td>
    </tr>
    <tr>
      <th>353</th>
      <td>8/1/18</td>
      <td>354</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.46</td>
    </tr>
    <tr>
      <th>354</th>
      <td>8/2/18</td>
      <td>355</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.46</td>
    </tr>
    <tr>
      <th>355</th>
      <td>8/3/18</td>
      <td>356</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.46</td>
    </tr>
    <tr>
      <th>356</th>
      <td>8/4/18</td>
      <td>357</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.46</td>
    </tr>
    <tr>
      <th>357</th>
      <td>8/5/18</td>
      <td>358</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.23</td>
    </tr>
    <tr>
      <th>358</th>
      <td>8/6/18</td>
      <td>359</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.23</td>
    </tr>
    <tr>
      <th>359</th>
      <td>8/7/18</td>
      <td>360</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.23</td>
    </tr>
    <tr>
      <th>360</th>
      <td>8/8/18</td>
      <td>361</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.23</td>
    </tr>
    <tr>
      <th>361</th>
      <td>8/9/18</td>
      <td>362</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.23</td>
    </tr>
    <tr>
      <th>362</th>
      <td>8/10/18</td>
      <td>363</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.23</td>
    </tr>
    <tr>
      <th>363</th>
      <td>8/11/18</td>
      <td>364</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.23</td>
    </tr>
    <tr>
      <th>364</th>
      <td>8/12/18</td>
      <td>365</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.07</td>
    </tr>
    <tr>
      <th>365</th>
      <td>8/13/18</td>
      <td>366</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.07</td>
    </tr>
    <tr>
      <th>366</th>
      <td>8/14/18</td>
      <td>367</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.07</td>
    </tr>
    <tr>
      <th>367</th>
      <td>8/15/18</td>
      <td>368</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.07</td>
    </tr>
    <tr>
      <th>368</th>
      <td>8/16/18</td>
      <td>369</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.07</td>
    </tr>
    <tr>
      <th>369</th>
      <td>8/17/18</td>
      <td>370</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.07</td>
    </tr>
    <tr>
      <th>370</th>
      <td>8/18/18</td>
      <td>371</td>
      <td>aug</td>
      <td>2018</td>
      <td>407.07</td>
    </tr>
    <tr>
      <th>371</th>
      <td>8/19/18</td>
      <td>372</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.84</td>
    </tr>
    <tr>
      <th>372</th>
      <td>8/20/18</td>
      <td>373</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.84</td>
    </tr>
    <tr>
      <th>373</th>
      <td>8/21/18</td>
      <td>374</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.84</td>
    </tr>
    <tr>
      <th>374</th>
      <td>8/22/18</td>
      <td>375</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.84</td>
    </tr>
    <tr>
      <th>375</th>
      <td>8/23/18</td>
      <td>376</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.84</td>
    </tr>
    <tr>
      <th>376</th>
      <td>8/24/18</td>
      <td>377</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.84</td>
    </tr>
    <tr>
      <th>377</th>
      <td>8/25/18</td>
      <td>378</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.84</td>
    </tr>
    <tr>
      <th>378</th>
      <td>8/26/18</td>
      <td>379</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.26</td>
    </tr>
    <tr>
      <th>379</th>
      <td>8/27/18</td>
      <td>380</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.26</td>
    </tr>
    <tr>
      <th>380</th>
      <td>8/28/18</td>
      <td>381</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.26</td>
    </tr>
    <tr>
      <th>381</th>
      <td>8/29/18</td>
      <td>382</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.26</td>
    </tr>
    <tr>
      <th>382</th>
      <td>8/30/18</td>
      <td>383</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.26</td>
    </tr>
    <tr>
      <th>383</th>
      <td>8/31/18</td>
      <td>384</td>
      <td>aug</td>
      <td>2018</td>
      <td>406.26</td>
    </tr>
  </tbody>
</table>
</div>



Puedes utilizar esta técnica también con una columna. Por ejemplo, si dices que solo te interesan los valores de partes de CO2 por millón, te refieres a esa columna y los corchetes para obtenerla, pero tienes un segundo conjunto de corchetes con la máscara y cuando lo hagas solo habrás devuelto los valores de partes de CO2 por millón, ninguno del resto del marco de datos, porque especificaste esta columna específica.


```python
# Podemos limitar lo que se devuelve haciendo referencia a una columna específica.
# y colocando la máscara en un soporte doble

data['CO2ppm'][mask]
```




    0      405.20
    1      405.20
    2      405.20
    3      405.20
    4      405.20
    5      405.20
    6      405.20
    7      404.54
    8      404.54
    9      404.54
    10     404.54
    11     404.54
    12     404.54
    13     404.54
    14     404.23
    15     404.23
    16     404.23
    17     404.23
    18     404.23
    353    407.46
    354    407.46
    355    407.46
    356    407.46
    357    407.23
    358    407.23
    359    407.23
    360    407.23
    361    407.23
    362    407.23
    363    407.23
    364    407.07
    365    407.07
    366    407.07
    367    407.07
    368    407.07
    369    407.07
    370    407.07
    371    406.84
    372    406.84
    373    406.84
    374    406.84
    375    406.84
    376    406.84
    377    406.84
    378    406.26
    379    406.26
    380    406.26
    381    406.26
    382    406.26
    383    406.26
    Name: CO2ppm, dtype: float64



Por lo general, viste que creamos una máscara, y la llamamos máscara, y estábamos escribiendo fuera de la máscara en nuestro código. Pero generalmente la gente no hace eso. Lo hacen mucho más simple, donde simplemente escriben la máscara.

Esta es la declaración booleana aquí, que he resaltado. Y ellos
simplemente colocan la máscara en una línea de código con los datos o la columna específica que desean. Esto es un poco complicado de ver, pero recuerda siempre ir primero a la máscara y estará en el segundo conjunto de corchetes o estará en el primer conjunto de corchetes y es solo una declaración booleana. Y devolverá las filas que son verdaderas para la declaración booleana. Y esta es una forma que obtiene los datos específicos que deseas.


```python
# Por lo general, la máscara se escribe directamente en la línea de código.
# Mire siempre al segundo juego de corchetes para ver
# que es la mascara

data['CO2ppm'][data['month']=='aug']
```




    0      405.20
    1      405.20
    2      405.20
    3      405.20
    4      405.20
    5      405.20
    6      405.20
    7      404.54
    8      404.54
    9      404.54
    10     404.54
    11     404.54
    12     404.54
    13     404.54
    14     404.23
    15     404.23
    16     404.23
    17     404.23
    18     404.23
    353    407.46
    354    407.46
    355    407.46
    356    407.46
    357    407.23
    358    407.23
    359    407.23
    360    407.23
    361    407.23
    362    407.23
    363    407.23
    364    407.07
    365    407.07
    366    407.07
    367    407.07
    368    407.07
    369    407.07
    370    407.07
    371    406.84
    372    406.84
    373    406.84
    374    406.84
    375    406.84
    376    406.84
    377    406.84
    378    406.26
    379    406.26
    380    406.26
    381    406.26
    382    406.26
    383    406.26
    Name: CO2ppm, dtype: float64


