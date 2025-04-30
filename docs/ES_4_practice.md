# Práctica con Pandas, Dataframes y Seaborn 🐼


---
## Exploración de datos

### Cargando e inspeccionando los datos

Después de visitar Michigan y aprender que se pueden cultivar uvas para vino (¡y que se puede hacer vino!) En un lugar tan frío, decides que te gustaría comenzar un viñedo allí. Has visto los viñedos y sabes que, aunque es posible cultivar uvas de vinificación allí, a veces hace demasiado frío. Uno se pregunta si, debido al cambio climático, Michigan pronto tendrá un clima más cálido y más adecuado para el cultivo de uvas.

Sabes que Europa tiene una larga historia de cultivo de uvas y te preguntas si mantuvieron registros que pudieran indicar cómo responden las uvas a los cambios de temperatura. Encuentras un [estudio](https://www.clim-past.net/8/1403/2012/cp-8-1403-2012.pdf) que ha recopilado numerosos registros de fechas de cosecha de uvas durante más de cuatro siglos y también una [base de datos](http://www.climatemonitor.it/?page_id=40210&lang=en) de anomalías de temperatura en Europa que se remontan a 1655.

Usando el conjunto de datos proporcionado, `grape_harvest.csv` (descarga [aquí](https://github.com/DanChitwood/PlantsAndPython/blob/master/grape_harvest.csv)), explora cómo la fecha de cosecha de la uva europea cambia con respecto a la temperatura a lo largo de siglos de datos.

Para comenzar, importa `pandas` en la celda siguiente: 


```python
# Importa pandas aquí



```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

    import pandas as pd
    ```

Luego, lee en `grape_harvest.csv` usando la función `pd.read_csv()` un marco de datos de pandas.


```python
# Lee los datos de la cosecha aquí
# Coloca grape_harvest.csv en el mismo directorio desde el que estás ejecutando este .ipynb
# Si está en un directorio diferente, deberás especificar la ruta al archivo 

# Alternativamente, puede leer los datos de GitHub usando la siguiente URL:
# https://raw.githubusercontent.com/DanChitwood/PlantsAndPython/master/grape_harvest.csv




```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

    # Lee los datos de la cosecha aquí
    # data = pd.read_csv("grape_harvest.csv")
    data = pd.read_csv("https://raw.githubusercontent.com/DanChitwood/PlantsAndPython/master/grape_harvest.csv")
    ```

Ahora, escribe un código para inspeccionar las propiedades de los datos y luego responde las siguientes preguntas:

Usa una función de pandas para mirar las primeras cinco líneas de datos:


```python
# Pon tu código aquí



```


??? success "Respuesta"
    ```python
    ### RESPUESTA ###

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
          <th>year</th>
          <th>region</th>
          <th>harvest</th>
          <th>anomaly</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>1700</td>
          <td>alsace</td>
          <td>42.9</td>
          <td>-0.91</td>
        </tr>
        <tr>
          <th>1</th>
          <td>1701</td>
          <td>alsace</td>
          <td>35.9</td>
          <td>-0.76</td>
        </tr>
        <tr>
          <th>2</th>
          <td>1702</td>
          <td>alsace</td>
          <td>45.0</td>
          <td>-1.40</td>
        </tr>
        <tr>
          <th>3</th>
          <td>1703</td>
          <td>alsace</td>
          <td>49.4</td>
          <td>-1.21</td>
        </tr>
        <tr>
          <th>4</th>
          <td>1704</td>
          <td>alsace</td>
          <td>30.4</td>
          <td>-0.44</td>
        </tr>
      </tbody>
    </table>
    </div>



Usa una función de pandas para ver las últimas cinco líneas de datos: 


```python
# Pon tu código aquí



```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

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
          <th>year</th>
          <th>region</th>
          <th>harvest</th>
          <th>anomaly</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>4727</th>
          <td>1873</td>
          <td>vendee_poitou_charente</td>
          <td>32.0</td>
          <td>0.06</td>
        </tr>
        <tr>
          <th>4728</th>
          <td>1874</td>
          <td>vendee_poitou_charente</td>
          <td>2.0</td>
          <td>-0.22</td>
        </tr>
        <tr>
          <th>4729</th>
          <td>1875</td>
          <td>vendee_poitou_charente</td>
          <td>29.0</td>
          <td>-1.02</td>
        </tr>
        <tr>
          <th>4730</th>
          <td>1876</td>
          <td>vendee_poitou_charente</td>
          <td>32.0</td>
          <td>-0.55</td>
        </tr>
        <tr>
          <th>4731</th>
          <td>1877</td>
          <td>vendee_poitou_charente</td>
          <td>34.0</td>
          <td>-0.56</td>
        </tr>
      </tbody>
    </table>
    </div>



Usa una función de pandas para ver un resumen de las estadísticas (como el recuento, el mínimo, el máximo y la media) para columnas con datos continuos:


```python
# Pon tu código aquí



```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

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
          <th>year</th>
          <th>harvest</th>
          <th>anomaly</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>count</th>
          <td>4732.000000</td>
          <td>4732.000000</td>
          <td>4732.000000</td>
        </tr>
        <tr>
          <th>mean</th>
          <td>1832.835376</td>
          <td>33.959510</td>
          <td>-0.337811</td>
        </tr>
        <tr>
          <th>std</th>
          <td>91.713152</td>
          <td>11.807714</td>
          <td>0.675309</td>
        </tr>
        <tr>
          <th>min</th>
          <td>1655.000000</td>
          <td>-13.000000</td>
          <td>-2.470000</td>
        </tr>
        <tr>
          <th>25%</th>
          <td>1762.000000</td>
          <td>25.900000</td>
          <td>-0.750000</td>
        </tr>
        <tr>
          <th>50%</th>
          <td>1834.500000</td>
          <td>34.000000</td>
          <td>-0.280000</td>
        </tr>
        <tr>
          <th>75%</th>
          <td>1903.000000</td>
          <td>42.600000</td>
          <td>0.060000</td>
        </tr>
        <tr>
          <th>max</th>
          <td>2007.000000</td>
          <td>75.000000</td>
          <td>1.460000</td>
        </tr>
      </tbody>
    </table>
    </div>



Utiliza una función de pandas para obtener los nombres de las columnas. 


```python
# Pon tu código aquí



```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

    data.columns
    ```



    ```python
    Index(['year', 'region', 'harvest', 'anomaly'], dtype='object')
    ```


Para una de las columnas que es una variable categórica, usa una función para enumerar todos los niveles para esa variable. 


```python
# Pon tu código aquí



```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

    data['region'].unique()
    ```



    ```python
    array(['alsace', 'auvergne', 'auxerre_avalon', 'beaujolais_maconnais',
           'bordeaux', 'burgundy', 'champagne_1', 'champagne_2',
           'gaillac_south_west', 'germany', 'high_loire_valley',
           'ile_de_france', 'jura', 'languedoc', 'low_loire_valley',
           'luxembourg', 'maritime_alps', 'northern_italy',
           'northern_lorraine', 'northern_rhone_valley', 'savoie',
           'southern_lorraine', 'southern_rhone_valley', 'spain',
           'switzerland_leman_lake', 'various_south_east',
           'vendee_poitou_charente'], dtype=object)
    ```



Para la variable categórica, también usa una función para determinar cuántas filas hay que representan cada nivel.


```python
# Pon tu código aquí


```

??? success "Respuesta"

    ```python
    ### RESPUESTA ##

    data['region'].value_counts()
    ```



    ```python
    switzerland_leman_lake    353
    burgundy                  350
    southern_rhone_valley     333
    jura                      306
    ile_de_france             302
    bordeaux                  274
    alsace                    262
    languedoc                 233
    spain                     231
    low_loire_valley          203
    champagne_2               183
    germany                   165
    northern_italy            156
    maritime_alps             136
    auxerre_avalon            128
    northern_lorraine         127
    northern_rhone_valley     126
    savoie                    123
    southern_lorraine         109
    luxembourg                107
    high_loire_valley          92
    various_south_east         82
    champagne_1                81
    auvergne                   80
    vendee_poitou_charente     75
    beaujolais_maconnais       73
    gaillac_south_west         42
    Name: region, dtype: int64
    ```


¿Cuántas filas hay en este conjunto de datos? 


```python
# Pon tu código aquí



```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

    print(len(data))
    ```

    4732


¡Felicitaciones por leer los datos y explorar su estructura! En la siguiente actividad, exploraremos la relación entre las fechas de cosecha de la uva y el clima. 
