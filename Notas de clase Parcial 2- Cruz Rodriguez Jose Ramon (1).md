`2da Parcial - Ejercicios de clase` 
---
###### **Cruz Rodriguez Jose Ramon**
-----------------------
**Sintaxis de una funcion**
``` python
def <function_name>([<parameters>]):
    <statement(s)>
```
* Las funciones permiten Modularidad
* Ejemplo de código sin modularidad
```python
# Programa Principal

# Código para leer un archivo csv
<sentencia 1>
<sentencia 2>
<sentencia 3>

# Código para procesar los datos de un archivo csv
<sentencia 4>
<sentencia 5>
<sentencia 6>

# Código para guardar los nuevos datos en el archivo csv
<sentencia 7>
<sentencia 8>
<sentencia 9>
```

* Ejempo con código modular:
```python

# Función para leer un archivo csv
def read_file():
    <sentencia 1>
    <sentencia 2>
    <sentencia 3>

# Función para procesar los datos de un archivo csv
def process_file():
    <sentencia 4>
    <sentencia 5>
    <sentencia 6>

# Función para guardar los nuevos datos en el archivo csv
def write_file():
    <sentencia 7>
    <sentencia 8>
    <sentencia 9>

# Programa Principal
read_file()
process_file()
write_file()
```


##### Caracteristicas:
###### **Definición de funciones:**

   - Para definir una función en Python, utilizamos la palabra clave `def`, seguida del nombre de la función y un par de paréntesis `()`. El nombre de la función debe seguir las reglas de nomenclatura de Python, que generalmente significa que debe consistir en letras, números y guiones bajos, y no puede comenzar con un número.
   - Después de los paréntesis, se coloca un colon `:` para indicar el comienzo del cuerpo de la función. El cuerpo de la función contiene una o más instrucciones que se ejecutarán cuando se llame a la función.

   Ejemplo:
```python
   def saludar():
       print("Hola, mundo!")
```
**-Declaración y llamada de funciones:**

* Una función se declaran con la palabra reservada *def*
* Una función puede recibir parámetros
* Una función puede retornar un valor, varios o ninguno
* Cuando no retorna nada de manera explícita, siempre retorna *None*
* Una función puede ser recursiva
* Sintaxis general de una función:

``` python
def <function_name>([<parameters>]):
    <statement(s)>
```

Donde:
| Elemento        | Significado                                                                      |
|-----------------|----------------------------------------------------------------------------------|
|def              | Palabra clave para indicar que se está **def**iniendo una función                |
|<function_name>  | Un identificador de Python válido que nombra a la función                        |
|\<parameters>    | Lista opcional separada por comas de parámetros que se pueden pasar a la función |
|:                | Símbolo que indica el final del encabezado o firma de la función de Python       |
|<statement(s)>   | Bloque de sentencias válidas de Python                                           |

* Para llamar a la función:
``` python
<function_name>([<arguments>])
```
* <arguments> son los valores pasados a la función.
* Corresponden a los <parameters> en la definición de la función.
* Se puede definir una función que no acepte ningún argumento, pero los paréntesis aún son necesarios.
* Tanto una definición de función como una llamada a función siempre deben incluir paréntesis, aunque estén vacíos.

###### **Parametros y argumentos:**

Las funciones pueden recibir cero o más parámetros (también llamados argumentos). Estos parámetros son valores que se pasan a la función y se utilizan en el cuerpo de la función para realizar cálculos o ejecutar acciones.
    * Sintaxis de una función:

``` python
def <function_name>([<parameters>]):
    <statement(s)>
```

* Llamada de una función:

```python
<function_name>([<arguments>])
```
###### **-Argumentos posicionales (obligatorios):**
* La forma más sencilla de pasar argumentos a una función de Python es con argumentos posicionales u obligatorios.
```python
def productos(producto, cantidad, precio):
    print(f" {cantidad} {producto} cuestan {precio} pesos")

productos("manzanas", 5, 7.5)
```
* Los parámetros (producto, cantidad y precio) se comportan como variables definidas localmente en la función.
* Cuando se llama a la función, los argumentos que se pasan ("manzanas", 5, 7.5) están vinculados a los parámetros en orden
* Los argumentos posicionales son la forma más sencilla de pasar datos a una función
* Ofrecen la menor flexibilidad.
* El orden de los argumentos en la llamada debe coincidir con el orden de los parámetros en la definición. 

 
###### **-Parámetros por defecto (default)**
* Se especifica en una definición de función de Python de la forma <nombre>=\<valor>
* \<valor> se convierte en un valor predeterminado para ese parámetro.
* Se denominan parámetros predeterminados u opcionales. 
* Ejmplo:
```python
def productos(producto="productos", cantidad="0", precio=0.0):
    print(f" {cantidad} {producto} cuestan {precio} pesos")

# Invocación sin argumentos
productos()
#-------------------------------------------
# Invocación con argumentos posicionales
productos("manzanas",5,5.5)
#---------------------------------------------
# Invocación con argumentos nombrados o de palabra clave
productos(producto="manzanas", cantidad=5, precio=5.5)
```
###### **-Valores de parámetros predeterminados mutables**
* Ejemplo:
```
def my_function(my_list=[]):   #"my_list"inicilaiza como lista vacia (valor por defecto de la funcion)
    my_list.append('???')
    return my_list
````

```
my_function(["a", "b", "c"])
```
['a', 'b', 'c', '???']

```
#Si se llama sin ningún argumento
print(my_function())
print(my_function())
print(my_function())
````
['???', '???']
['???', '???', '???']
['???', '???', '???', '???']

-----

###### **-Retorno de valores y uso de palabra clave "return":**
* Una instrucción *return* en una función de Python tiene dos propósitos:
1. Al terminar la función devuelve el control de ejecución a partir de donde se llamó.
2. Proporciona un mecanismo para regresar datos donde se llamó o asignó.
```python
def f1():             
    print("Hola")
    print("Mundo")
    return

f1()
```
Hola
Mundo
```python
def f2():             
    print("Hola")
    print("Mundo")
f2()
```
Hola
Mundo
* *return* no necesita estar al final de una función.
* Pueden aparecer en cualquier parte del cuerpo de una función
* Puede aparecer incluso varias veces 

#### Funciones sin valor de retorno (None).
* Puede usarse para la comprobación de errores

```python
def f():
    if error_cond1:
        return
    if error_cond2:
        return
    if error_cond3:
        return

    <normal processing>
````
* Cuando no se da ningún valor de retorno, una función devuelve el valor especial None
```def f():
    return


print(f())
`````
None

--------------------------
#### Valor de retorno en funciones:
* Una función puede devolver cualquier tipo de objeto.
 Ejemplo: diccionario
```python
names =  dict(name_1='Hugo', name_2='Paco', name_3='Luis') #hecho en clase
names
```
{'name_1': 'Hugo', 'name_2': 'Paco', 'name_3': 'Luis'}

* Retornar listas que se pueden indizar o dividir:
```python
names =  dict(name_1='Hugo', name_2='Paco', name_3='Luis') #hecho en clase
names
```
['a', 'b', 'c', 'd', 'e']

##### **Recursion:**
##### Definición de funciones recursivas.
Una definición recursiva es aquella en la que el término definido aparece en la propia definición.
* Capacidad de una función de llamarse a sí misma
* La mayoría de los problemas de programación se pueden resolver sin recursividad. 
* Entonces... la recursividad no suele ser necesaria.
```python
def contar_hasta_n(n):
    if n <= 0:
        return
    else:
        print(n)
        contar_hasta_n(n - 1)

contar_hasta_n(5)
```
En este ejemplo, la función contar_hasta_n" toma un número "n" como argumento y, si "n" es mayor que 0, imprime el valor de "n" y luego llama a la función "contar_hasta_n" con "n-1". Esto crea una serie de llamadas recursivas que imprimirán los números en orden descendente desde "n" hasta 1. Cuando "n" llega a 0, la función se detiene, lo que sirve como el caso base de la recursión.
* Las funciones recursivas suelen un patrón:
    * Hay uno o más casos base que se pueden resolver directamente sin necesidad de más recursividad.
    * Cada llamada recursiva acerca progresivamente la solución a un caso base (mecanismo de retorno).
##### Casos base y casos recursivos:
* Ejemplo: Cuenta regresiva hasta cero
```python
# cuenta regresiva no recursiva (iterativa)
def cuenta_regresiva(n):
    while n >= 0:
        print(n)
        n -= 1
cuenta_regresiva(5)
```
 5
 4
 3
 2
 1
 0
 
````python
# cuenta regresiva recursiva
def cuenta_regresiva(n):
    print(n)
    if n == 0:
        return                      # Fin de la recursión, caso base
    else:
        cuenta_regresiva(n - 1)     # Llamada recursiva
cuenta_regresiva(5)
````
5
4
3
2
1
0
* El caso base se produce cuando n es cero, momento en el que se detiene la recursividad.
En la llamada recursiva, el argumento es uno menos que el valor actual de n, por lo que cada recursividad se acerca al caso base.
-----
* Calcular el tiempo de ejecución (evaluación empírica)
* timeit(<command>, setup=<setup_string>, number=<iterations>)
```
# Ejemplo iterativo
from timeit import timeit

timeit("print(string)", setup="string='Hola Mundo'", number=100)
````
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
...
Hola Mundo
Hola Mundo
Hola Mundo
Hola Mundo
Output is truncated. View as a scrollable element or open in a text editor. Adjust cell output settings...
0.0007953000022098422

### Documentación y Comentarios
####  Uso de docstrings para documentar funciones.
```
def suma(a, b):
    """
    This function adds two numbers.

    Parameters:
    a (int): The first number.
    b (int): The second number.

    Returns:
    int: The sum of a and b.
    """
    return a + b

def resta(a, b):
    """
    This function subtracts two numbers.

    Parameters:
    a (int): The first number.
    b (int): The second number.

    Returns:
    int: The difference between a and b.
    """
    return a - b

def multiplicacion(a, b):
    """
    This function multiplies two numbers.

    Parameters:
    a (int): The first number.
    b (int): The second number.

    Returns:
    int: The product of a and b.
    """
    return a * b

def division(a, b):
    """
    This function divides two numbers.

    Parameters:
    a (int): The first number.
    b (int): The second number.

    Returns:
    float: The quotient of a and b.
    """
    return a / b
````

```
print(suma.__doc__)
````
This function adds two numbers.

    Parameters:
    a (int): The first number.
    b (int): The second number.

    Returns:
    int: The sum of a and b.


------------------------------------------------------
## Ejercicios en "Guizero":
##### **`-Creando una Aplicación GUI con Guizero`**

El siguiente código es un ejemplo de cómo crear una aplicación de interfaz gráfica de usuario (GUI). Esta aplicación creará una ventana con el título "Hello world".

```python
from guizero import App

# Crear una instancia de la aplicación con el título "Hello world"
app = App(title="Hello world")

# Mostrar la ventana de la aplicación
app.display()
````
**"from guizero import App"**: Esta línea importa la clase App de la biblioteca guizero, que se utilizará para crear la aplicación GUI.

**"app = App(title="Hello world")"**: Aquí se crea una instancia de la aplicación (app) con un título específico, que en este caso es "Hello world".

**"app.display()"**: Esta línea muestra la ventana de la aplicación en la pantalla del usuario, lo que permite interactuar con la interfaz gráfica.

-----------------------------------------
##### **`-Creando una Aplicación GUI que muestra un mensaje luego de oprimir un boton generado`**
````python
from guizero import App, Text, PushButton
# Definir una función llamada say_hello que se ejecutará cuando se haga clic en el botón
def say_hello():
    message_2.value = "ICI Rocks!"  # Cambia el valor de message_2 cuando se hace clic

app = App("ICI App")

# Crear un objeto "Text" llamado "message" y mostrar un mensaje en la ventana de la aplica-ción
message = Text(app, text="Welcome to the ICI App!")
message_2=Text(app)
button = PushButton(app, text="Click me!", command=say_hello)

app.display()

````
**1.-** Importa las clases App, Text y PushButton de la biblioteca guizero.

**2.-** Define una función llamada "say_hello" que se ejecutará cuando se haga clic en el botón. Esta función cambia el valor del objeto "message_2" a "ICI Rocks!".

**3.-** Crea una instancia de la clase "App" llamada "ICI App". Esto crea la ventana principal de la aplicación.

**4.-** Crea un objeto Text llamado "message" y muestra el mensaje "Welcome to the ICI App!" en la ventana de la aplicación.

**5.-** Crea un objeto Text llamado "message_2", que inicialmente no contiene ningún texto. Este objeto se utilizará para mostrar un mensaje diferente cuando se haga clic en el botón.

**6.-** Crea un botón llamado "button" con el texto "Click me!" y lo asocia a la función say_hello utilizando el parámetro command.

------------------------------------



