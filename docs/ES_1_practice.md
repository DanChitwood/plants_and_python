# Prática

## Práctica con Variables, Funciones, Listas e Índices
________

**¡Ahora inténtalo tú!**

Piensa en tu planta favorita. Puede ser un alimento o una flor que te guste. Acabas de conocer la notable diversidad de las plantas, desde las algas hasta las plantas terrestres, ¡hay muchas para elegir!

Busca en Google tu planta favorita y encuentra su nombre en latín, tanto el género como el epíteto de la especie.

**Haz esto:**

En la celda de abajo, crea dos variables, `genero` y `especie`. Asigna a las variables los nombres del género y del epíteto de la especie de tu planta favorita.

Luego, crea una nueva variable llamada `my_fav` que combine los nombres de género y especie juntos. **Sugerencia:** coloca un guión bajo `_` delante del nombre de la especie para que cuando combines el género y la especie queden separados.

Finalmente, utiliza la función de impresión `print()` para imprimir tus especies favoritas.


```python
# Pon tu código y tu respuesta aquí


```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

    genero = "Jacaranda"
    especie = "_mimosifolia"
    my_fav = genero + especie
    print(my_fav)
    ```

    Jacaranda_mimosifolia


Ahora, utilizando wikipedia, busca el género de tu planta favorita. Encuentra otras dos especies del mismo género que tu planta favorita. 

**Haz esto:**

Crea dos nuevas variables, `especie1` y `especie2`. Usando la variable `genero` que creaste previamente y las cadenas para los epítetos de las dos nuevas especies, asigna a las dos nuevas variables de especies los nombres completos (con género) de las dos nuevas especies.


```python
## Pon tu código y tu respuesta aquí

```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

    especie1 = genero + "_ulei"
    especie2 = genero + "_caerulea"
    ```

Por último, cree una lista con el nombre de su género con sus variables "my_fav", "especie1" y "especie2". A continuación, utilizando indexación con su lista, imprime el nombre de tu especie favorita.


```python
# Pon tu código y tu respuesta aquí

```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

    jacaranda = [my_fav, especie1, especie2]
    print(jacaranda[0])
    ```

    Jacaranda_mimosifolia


## Práctica con rebanar y tipos de datos
____

En el vídeo has aprendido sobre el ángulo áureo, un número irracional basado en la proporción áurea y la secuencia de Fibonacci que aparece a menudo en la naturaleza. En las plantas, el ángulo áureo determina el ángulo filotáctico, es decir,la disposición de las hojas y otros órganos en las plantas. Por ejemplo, la hermosa disposición de las flores en un girasol. En lecciones posteriores calcularás tú mismo el Ángulo de Oro utilizando bucles y utilizarás el valor para modelar el crecimiento de un girasol.

¿Qué es la secuencia de Fibonacci? Aprenderemos más adelante, pero es una secuencia de números en la que cada número de la serie es la suma de los dos números anteriores.

En la celda de abajo, la lista `fibonacci` tiene los primeros 16 números de la serie. Ejecuta la celda para crear la lista y mírala, verificando que cada número es la suma de los dos anteriores.


```python
fibonacci = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987]
```

En la celda de abajo, utiliza la función `len()` para verificar que hay 16 números en esta lista.


```python
# Pon tu código y tu respuesta aquí
```

??? success "Respuesta"
    ```python
    ### RESPUESTA ###

    len(fibonacci)
    ```

    16



La secuencia de Fibonacci tiene propiedades matemáticas especiales. Por ejemplo, cada enésimo elemento de la serie es divisible por el enésimo elemento. Por ejemplo, el tercer elemento de la serie es `2`. Todos los demás elementos deben ser pares. El cuarto elemento de la serie es `3`. Cada cuarto elemento debe ser divisible por `3`.

En el último vídeo, aprendiste sobre el rebanado y cómo utilizar un valor de `step` para seleccionar cada enésimo elemento de una serie.

Vamos a explorar esta interesante propiedad de la serie de Fiobonacci.

**Haz esto:**

En la celda de abajo, empezando por el 4º elemento de la serie, selecciona cada 4º número a partir de ahí. ¿Cuál es el 4º elemento y todos los números que has cortado son divisibles por él?

**Sugerencia:** Recuerda que el primer elemento de una lista está indexado como 0 y el enésimo elemento de la lista no está indexado como n.


```python
# Pon tu código y tu respuesta aquí
```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

    fibonacci[3::4]
    ```

    [3, 21, 144, 987]



Pruébalo para el 5º elemento de la serie, y selecciona cada 5º número a partir de entonces.


```python
# Pon tu código y tu respuesta aquí
```

??? success "Respuesta"

    ```python
    ### RESPUESTA ###

    fibonacci[4::5]
    ```

    [5, 55, 610]


