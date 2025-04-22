# Coding cells / Celdas de código
_____

**Watch this video from 3:33 to 9:51 / Mira este video de 3:33 a 9:51**  
Para español, haga click en configuración, seleccione "español" debajo de los subtítulos. Traducción por Dra. Alejandra Rougon (UNAM ENES León, México)


<iframe width="560" height="315" src="https://www.youtube.com/embed/FrDYpLVuTkQ?si=CAiRhcmhc_ZHj-Ov&amp;start=213" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


=== "English :flag_us:" 

    You're going to learn all about how to create variables and how to code in the coming lessons, but let's just do some very simple code to just see how Jupyter works. Let's create code to calculate the area of a circle. Creating variables in Jupyter is easy, you just pick a name. Once you pick a name you use the equal sign to assign them a value. Values assigned to variables can either be strings of characters, they're called strings, or they can be numbers. Let's create a string of characters first. To create a string you always use quotation marks and let's set the value to `"pi_is_a_number"`. That is what our variable `pi` will be. Once you put your code in your cell, you need to execute the cell. You need to tell the cell to process the code that is in it. To execute a cell, all you do is you press shift + enter. You can see that a number appears saying that our cell has been processed and a new cell appears below.  


    ```python
    pi = "pi_is_a_number"
    ```

    Maybe we want to double check that in fact `pi` is set to the value `"pi_is_a_number"` so we simply type `pi` alone and we press shift + enter and the output, what is returned to us by Jupyter, is `"pi_is_a_number"`. So we had set `pi` to that string. 

    ```python
    pi
    ```

    `'pi_is_a_number'`

    Maybe, though, we really want `pi` to actually be a number. So we just write again `pi` equals 3.14159 and we press shift + enter again. We want to see has `pi` been assigned the correct value and it is now 3.14159.

    ```python
    pi = 3.14159
    ```

    ```python
    pi
    ```

    `3.14159`

    Notice that it's very easy for us to create a variable, but it's also very easy for us to write over a variable and notice too that the order that we execute cells matters. This will be important later when you're writing code, that the order that you execute the cells is the code that you're executing and it affects the assignment of values to variables and that very much can affect your code. So order does matter.  

    Let's create some more variables. Let's create a variable `r` for radius, set it equal to one. Something that's very important in coding is commenting. If you use the `#` any characters or writing after the hashtag will not be processed by Python. It's a convenient way to leave comments in your code and help guide you in the future of what your code actually means, so we should get in the into the practice of using comments often. Let's remind us what this variable was. We can say `# r is radius`. You can create multiple lines of code within one cell. Let's create another variable. We'll call it `A` for area. It matters whether something is lowercase or uppercase, so you have to keep track of that, and if this is the area of the circle, let's say that it is `pi` times `r` squared and notice that an asterisk, one asterisk, is for multiplication. Two asterisks is for exponents. So we can hit shift + enter. We have assigned the value to `r` and using `r` and `pi` we then have calculated `A`. So let's see what `A` is equal to and the area of our circle is equal to  3.14159, as we would expect.


    ```python
    r = 1 # r is radius

    A = pi*r**2
    ```

    ```python
    A
    ```

    `3.14159`

    When you have code, it's really easy with variables to reassign their values and this way it's really easier to tinker with things and do calculations. That's one of the powers of coding. So let's give an arbitrary number with a complicated decimal to our radius and if we recalculate the area of the circle now we can see that it's a much more different and complicated number.


    ```python
    r = 4.234678236728465724 # r is radius

    A = pi*r**2
    ```


    ```python
    A
    ```

    56.336561948104276


    As you saw math is trivial and easy to do in python. `+` is to create a sum, `-` is to subtract, as you saw `*` is for multiplication, `/` is for division, as you saw `**` is for exponents. There's also things called Boolean statements in computing that are very important. Boolean statements can evaluate only to `True` or `False`. These are  statements that create conditions that can only be said to be `True` or `False`. For example, maybe we want to say that 3 is greater than or equal `>=` to pi. That is not true, because 3 is less than pi, but if we evaluate this statement it comes out as `False`.


    ```python
    3 >= pi
    ```

    `False`

    So if we now say a Boolean statement of 3 is less than or equal `<=` to pi,that statement will be `True`.

    ```python
    3 <= pi
    ```

    `True`

    And if we said 3.14159 is not equal `!=` to pi that statement is `False` because 3.14159 is equal to pi. 

    ```python
    3.14159 != pi
    ```

    `False`

    We could say 3.14159 is double equal `==` to pi.  This is a computational way to say equals, because we're using just a single equal sign `=` to  assign variables, but here we really mean, is 3.14159 equal to pi, and that is a `True` statement.  


    ```python
    3.14159 == pi
    ```

    `True`

    You will also learn a lot about functions. You give inputs to functions and they give you outputs back. The simplest function is `print()`, which will simply give you back the value of a variable. So we can say `print(pi)` and we can see that the print function gives us back 3.14159 from the variable `pi`.


    ```python
    print(pi)
    ```

    `3.14159`


    So that's about coding cells. You're going to learn a lot more about coding in the following lessons.

=== "Español :flag_mx:"

    Aprenderás todo sobre cómo crear variables y cómo programar en las próximas lecciones. Pero hagamos un código muy simple para ver cómo funciona Jupyter. Vamos a crear código para calcular el área de un círculo. Crear variables en Jupyter es fácil, simplemente elige un nombre. Una vez que eliges un nombre, usa el signo igual '=' para asignarles un valor. Los valores asignados a las variables pueden ser cadenas de caracteres, se llaman cadenas (strings), o pueden ser números. Primero creemos una cadena de caracteres. Para crear una cadena, siempre usa comillas. Después establecemos el valor que será `"pi_is_a_number"`. Eso es lo que será nuestra variable `pi`. Una vez que pongas tu código en la celda, debes ejecutar la celda. Tienes que decirle a la celda que procese el código que contiene. Para ejecutar una celda, todo lo que debes hacer es presionar shift + enter. Puedes ver que aparece un número que dice que nuestra celda ha sido procesada y aparece una nueva celda debajo.


    ```python
    pi = "pi_is_a_number"
    ```

    Tal vez queramos volver a comprobar que, de hecho, `pi` está configurado con el valor `"pi_is_a_number"`, por lo que simplemente escribe sólo `pi` y presiona shift + enter y la salida. Lo que nos devuelve Jupyter es `"pi_is_a_number"`. Así que hemos establecido que pi esté asignado a esa cadena.


    ```python
    pi
    ```

    'pi_is_a_number'

    Pero quizás realmente queremos que `pi` sea un número. Entonces simplemente escribimos nuevamente `pi` igual a 3.14159 y presionamos shift + enter nuevamente. Queremos ve que se ha asignado a `pi` el valor correcto y ahora es 3.14159. 


    ```python
    pi = 3.14159
    ```


    ```python
    pi
    ```

    `3.14159`

    Ten en cuenta que es muy fácil para nosotros crear una variable, pero también es muy fácil para nosotros escribir sobre una variable y tomaen cuenta también que el orden en el que ejecutemos las celdas importa. Esto será importante más adelante cuando escribas código. El orden en que ejecutas las celdas es el código que estás ejecutando y afecta a la asignación de valores a variables y eso puede afectar mucho tu código. Entonces el orden sí importa.

    Creemos algunas variables más. Creemos una variable `r` para el radio, configúrala igual a uno. Algo que es muy importante en la programación es comentar. Si usas el hash `#` cualquier carácter que escribas después de él no será procesado por Python. Es una forma conveniente de dejar comentarios en tu código. Eso te puede ayudar a guiarte en el futuro para recordarlo que significa su código. Por eso, deberíamos entrar en la práctica de usar comentarios con frecuencia. Recordemos cuál era esta variable. Podemos escribir `# r es radio`. Puedes crear varias líneas de código dentro de una celda. Vamos a crear otra variable. La llamaremos `A` de área. Importa si algo está en minúsculas o en mayúsculas. Sí que tienes que recordar cómo escribiste tus variables. Si esta es el área del círculo, digamos que es `pi` multiplicado por `r` al cuadrado. Observa que un asterisco, es para la multiplicación. Dos asteriscos es para exponente o potencia. Ahora podemos presionar shift + enter. Hemos asignado el valor a `r`. Y usando `r` y `pi` entonces hemos calculado `A`. Así que veamos a qué es igual `A` y el área de nuestro círculo es igual a 3.14159, como esperábamos. 


    ```python
    r = 1 # r is radius

    A = pi*r**2
    ```


    ```python
    A
    ```

    `3.14159`


    Cuando tienes código, es muy fácil reasignar los valores de las variables. Y de esta manera es realmente más fácil jugar con las cosas y hacer cálculos. Ese es uno de los poderes de la programación. Así que demos un número arbitrario con un decimal complicado a nuestro radio. Y si recalculamos el área del círculo, ahora podemos ver que es un número mucho más diferente y complicado. 


    ```python
    r = 4.234678236728465724 # r is radius

    A = pi*r**2
    ```

    ```python
    A
    ```

    `56.336561948104276`

    Como viste, las matemáticas son triviales y fáciles de hacer en Python. `+` es para crear una suma, `-` es restar, como viste `*` es para multiplicar, `/` es para división, y `**` es para exponentes. También, en informática hay cosas llamadas declaraciones booleanas, que son muy importantes. Las declaraciones booleanas solo pueden evaluarse como `Verdadero` o `Falso`. Estas son declaraciones que crean condiciones de las que solo se puede decir `Verdadero` o `Falso`. Por ejemplo, tal vez queremos decir que 3 es mayor o igual `>=` a pi. Eso no es verdad, porque 3 es menor que pi, pero si evaluamos esta afirmación, nos da `Falso`.


    ```python
    3 >= pi
    ```

    `False`

    Entonces, si ahora decimos que una declaración booleana de 3 es menor o igual `<=` a pi, esa declaración será `Verdadero`.


    ```python
    3 <= pi
    ```

    `True`

    Y si dijimos que 3.14159 no es igual `!=` a pi, esa declaración es `Falso` porque 3.14159 es igual a pi. 


    ```python
    3.14159 != pi
    ```

    `False`


    Podríamos decir que 3.14159 es doble igual `==` a pi. Esta es una forma computacional de decir igual, porque estamos usando un solo signo igual `=` para asignar variables, pero aquí realmente queremos decir que 3.14159 es igual a pi, y esa es una declaración `Verdadera`.


    ```python
    3.14159 == pi
    ```

    `True`

    También aprenderás mucho sobre funciones. Le das entradas a funciones y ellas te regresan salidas. La función más simple es `print()`, que simplemente te devolverá el valor de una variable. Entonces podemos decir `print(pi)` y podemos ver que la función de impresión nos devuelve 3.14159 de la variable `pi`.


    ```python
    print(pi)
    ```

    `3.14159`


    Así que en esta lección hasta aquí veremos sobre programar en celdas. Vas a aprender mucho más sobre programación en las siguientes lecciones.
