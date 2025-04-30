# Data exploration

## Loading and inspecting the data

After visiting Michigan and learning that wine grapes can be grown (and that wine can be made!) in such a cold place, you decide that you would like to start a vineyard there. You've seen the vineyards and know that, although it is possible to grow wine grapes there, that sometimes it is too cold. You wonder if because of climate change, Michigan might soon have a warmer, more suitable climate for growing grapes. 

You know that Europe has a long history of growing grapes, and you wonder if they kept records that might indicate how grapes respond to changes in temperature. You find a [study](https://www.clim-past.net/8/1403/2012/cp-8-1403-2012.pdf) that has compiled numerous records of grape harvest dates for more than four centuries and also a [database](http://www.climatemonitor.it/?page_id=40210&lang=en) of temperature anomalies in Europe dating back to 1655.

Using the provided dataset, `grape_harvest.csv` (download [here](https://github.com/DanChitwood/PlantsAndPython/blob/master/grape_harvest.csv)), you're going to explore how the European grape harvest date changes with respect to temperature across centuries of data.

To get started, import `pandas` in the cell below:


```python
# Import pandas here



```

??? success "Answer"

    ```python
    ### ANSWER ###

    import pandas as pd
    ```

Then, read in `grape_harvest.csv` using the `pd.read_csv()` function a pandas dataframe.


```python
# Read in the grape harvest data here
# Put grape_harvest.csv in the same directory you are running this .ipynb from
# If in a different directory, you will need to specify the path to the file

# Alternatively, you can read in the data from GitHub using the following url:
# https://raw.githubusercontent.com/DanChitwood/PlantsAndPython/master/grape_harvest.csv


```

??? success "Answer"
    ```python
    ### ANSWER ###

    # Read in the grape harvest data here
    # data = pd.read_csv("grape_harvest.csv")

    # Or read in by url from GitHub

    data = pd.read_csv("https://raw.githubusercontent.com/DanChitwood/PlantsAndPython/master/grape_harvest.csv")
    
    ```


Now, write some code to inspect the properties of the data and then answer the following questions:

Use a pandas function to look at the first five lines of data:


```python
# Put your code here



```

??? success "Answer"

    ```python
    ### ANSWER ###

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



Use a pandas function to look at the last five lines of data:


```python
# Put your code here



```

??? success "Answer"

    ```python
    ### ANSWER ###

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



Use a pandas function to look at summary statistics (like the count, min, max, and mean) for columns with continuous data:


```python
# Put your code here



```
??? success "Answer"

    ```python
    ### ANSWER ###

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



Use a pandas function to retrieve the names of the columns. 


```python
# Put your code here



```


??? success "Answer"

    ```python
    ### ANSWER ###

    data.columns
    ```

    ```python
    Index(['year', 'region', 'harvest', 'anomaly'], dtype='object')
    ```

    

For one of the columns that is a categorical variable, use a function to list all the levels for that variable.


```python
# Put your code here



```

??? success "Answer"

    ```python
    ### ANSWER ###

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


For the categorical variable, also use a function to determine how many rows there are representing each level.


```python
# Put your code here


```

??? success "Answer"

    ```python
    ### ANSWER ###

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

How many rows are in this dataset?


```python
# Put your code here



```

??? success "Answer"

    ```python
    ### ANSWER ###

    print(len(data))
    ```

    4732


Congratulations on reading in the data and exploring its structure! In the next activity, we will be exploring the relationship between grape harvest dates and climate!
