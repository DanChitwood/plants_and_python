# 1.1 Funciones
## Nuestra primera función: `print()`
_______

***Mira este video de 2:28 a 3:35***

Para español, haga click en configuración, seleccione "español" debajo de los subtítulos.

Traducción por Alice Luckie (UNAM ENES León, México)


```python
# Para reproducir el siguiente tutorial, presiona shift + enter

from IPython.display import YouTubeVideo
from datetime import timedelta
start=int(timedelta(hours=0, minutes=2, seconds=28).total_seconds())
end=int(timedelta(hours=0, minutes=3, seconds=35).total_seconds())

YouTubeVideo("4XIllJVnT4Y",start=start,end=end,width=640,height=360)
```





<iframe
    width="640"
    height="360"
    src="https://www.youtube.com/embed/4XIllJVnT4Y?start=148&end=215"
    frameborder="0"
    allowfullscreen
></iframe>




***La siguiente es una transcripción del video.***

>💡 ***Recuerde:*** En el cuaderno anterior, creó una variable llamada `genus`. Vuelva a crear la variable `genus` en la celda de abajo para completar esta lección.


```python
# # Crea la variable `genus`

genus = "Vitis"
```

También puede recuperar el valor de una variable usando una función. Así que repasemos nuestra primera función, la más simple que es `print()`. Una función en Python tiene un nombre como print y tiene un par de paréntesis. Pones una entrada entre paréntesis y la función procesa la entrada para producir una salida. Entonces, por ejemplo, la salida de 
la función `print()` es simplemente imprimir el valor de nuestra variable. Entonces, si imprimimos `genus`, lo que obtenemos es `"Vitis"`.


```python
# Puede usar la función print() para ver un valor de variable
# Una función siempre tiene un paréntesis
# Colocas la entrada entre paréntesis
# La función procesa la entrada para producir una salida
# La salida de la función print() es imprimir nuestra variable

print(genus)
```

    Vitis


Puede usar comas para separar las salidas de la función `print()` por un 
espacio y se pueden usar tanto variables como cadenas con la función de impresión. Entonces, por ejemplo, en nuestra función `print()`, si ponemos una cadena entre comillas `"The variable genus is equal to"` y luego ponemos una coma y luego ponemos nuestra variable `genus`, y ejecutamos la función print lo que obtenemos es `The variable genus is equal to "Vitis"`.


```python
# Use comas para separar las salidas de print() por un espacio
# Tanto las variables como las cadenas se pueden usar con print()

print("The variable genus is equal to", genus)
```

    The variable genus is equal to Vitis

