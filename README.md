PRIMERA UNIDAD
# **Ejercicio: Implementación de la instrucción foreach**

Imagine que trabaja para una empresa de fabricación. La empresa necesita que complete un inventario de su almacén para determinar el número de productos que están listos para enviarse. Además del número total de productos terminados, debe informar del número de productos terminados almacenados en cada contenedor individual del almacén, junto con una suma acumulativa. Esta suma acumulativa se usará para crear una pista de auditoría para que pueda comprobar el trabajo e identificar la "reducción".

## **Recorrido en bucle de una matriz con "foreach"**

La instrucción `foreach` ofrece una manera sencilla y limpia de iterar los elementos de una matriz. La instrucción `foreach` procesa los elementos de matriz en orden creciente de índice, comenzando con el índice 0 y terminando con el índice Length - 1. Usa una variable temporal para contener el valor del elemento de matriz asociado a la iteración actual. Cada iteración ejecutará el bloque de código que se encuentra debajo de la declaración `foreach`.

A continuación, se muestra un ejemplo sencillo:

```csharp
string[] names = { "Rowena", "Robin", "Bao" };
foreach (string name in names)
{
    Console.WriteLine(name);
}
```

Debajo de la palabra clave `foreach`, el bloque de código que contiene `Console.WriteLine(name);` se ejecutará una vez para cada elemento de la matriz `names`. Dado que el runtime de .NET recorre en bucle cada elemento de la matriz, el valor almacenado en el elemento actual de la matriz `names` se asigna a la variable temporal `name` para facilitar el acceso al bloque de código.

Si ejecutara el código, vería el siguiente resultado.

```
Rowena
Robin
Bao
```

Use la instrucción `foreach` para crear una suma de todos los elementos disponibles en cada contenedor del almacén.

### **Crear e inicializar una matriz de números enteros (int).**

1. Asegúrese de que tiene un archivo Program.cs vacío abierto en Visual Studio Code.
    
    Si es necesario, abra Visual Studio Code y, luego, lleve a cabo los pasos siguientes para preparar un archivo Program.cs en el editor:
    
    1. En el menú **Archivo**, seleccione **Abrir carpeta**.
    2. Use el cuadro de diálogo "Abrir carpeta" para ir a la carpeta **CsharpProjects**.
    3. En el panel EXPLORADOR de Visual Studio Code, seleccione **Program.cs**.
    4. En el menú **Selección** de Visual Studio Code, elija **Seleccionar todo** y presione la tecla Supr.
2. Para crear una matriz de tipo `int` que almacene el número de productos terminados en cada contenedor, escriba el código siguiente:
    
    ```csharp
    int[] inventory = { 200, 450, 700, 175, 250 };
    ```
    

### **Agregar una instrucción foreach para recorrer en iteración la matriz.**

1. Para crear una instrucción `foreach` que recorra en iteración cada elemento de la matriz `inventory`, escriba el código siguiente:
    
    ```csharp
    foreach (int items in inventory)
    {
    
    }
    ```
    
    Observe que la instrucción `foreach` asigna temporalmente el valor del elemento de matriz actual a una variable `int` denominada `items`.
    
2. Asegúrese de que el código coincide con lo siguiente:
    
    ```csharp
    int[] inventory = { 200, 450, 700, 175, 250 };
    
    foreach (int items in inventory)
    {
    
    }
    ```
    

### **Agregar una variable para sumar el valor de cada elemento de la matriz.**

1. Coloque el cursor en la línea de código en blanco encima de la instrucción `foreach`.
2. Para declarar una nueva variable que represente la suma de todos los productos terminados que hay en el almacén, escriba el código siguiente:
    
    ```csharp
    int sum = 0;
    ```
    
    Asegúrese de declarar la variable **fuera** de la instrucción `foreach`.
    
3. Coloque el cursor dentro del bloque de código de la instrucción `foreach`.
4. Para agregar el valor actual almacenado en `items` a la variable `sum`, escriba el código siguiente:
    
    ```csharp
    sum += items;
    ```
    
5. Asegúrese de que el código coincide con lo siguiente:
    
    ```csharp
    int[] inventory = { 200, 450, 700, 175, 250 };
    int sum = 0;
    foreach (int items in inventory)
    {
        sum += items;
    }
    ```
    

### **Mostrar el valor final de suma.**

1. Cree una línea de código en blanco debajo del bloque de código de la instrucción `foreach`.
2. Para notificar la suma final de los elementos del inventario, escriba el código siguiente:
    
    ```csharp
    Console.WriteLine($"We have {sum} items in inventory.");
    ```
    
3. Asegúrese de que el código coincide con lo siguiente:
    
    ```csharp
    int[] inventory = { 200, 450, 700, 175, 250 };
    int sum = 0;
    foreach (int items in inventory)
    {
        sum += items;
    }
    
    Console.WriteLine($"We have {sum} items in inventory.");
    ```
    
4. En el menú **Archivo** de Visual Studio Code, seleccione **Guardar**.
5. En el panel EXPLORADOR, para abrir un terminal en la ubicación de la carpeta TestProject, haga clic con el botón derecho en **TestProject** y seleccione **abrir en terminal integrado**.
6. En el símbolo del sistema del terminal, escriba  **dotnet run** y presione Intro.
    
    ```
    We have 1775 items in inventory.
    ```
    

### **Crear una variable que contenga el número del contenedor actual y que muestre la suma acumulativa**

Para cumplir el requisito final del proyecto de informe de inventario, es necesario crear una variable que contenga la iteración actual de la instrucción `foreach` para que podamos mostrar el contenedor y el número de elementos terminados en ese contenedor, junto con la suma acumulativa de todos los elementos de los contenedores que se han contabilizado hasta el momento.

1. Agregue una nueva línea de código en blanco encima de la instrucción `foreach`.
2. Para declarar la variable `int` denominada `bin` que se inicializa en `0`, escriba el código siguiente:
    
    ```csharp
    int bin = 0;
    ```
    
    Usará `bin` para almacenar el número del contenedor cuyo inventario se está procesando actualmente.
    
3. Dentro del bloque de código `foreach`, para incrementar `bin` cada vez que se ejecuta el bloque de código, escriba el código siguiente:
    
    ```csharp
    bin++;
    ```
    
    Observe que usa el operador `++` para incrementar el valor de la variable en 1. Se trata de un acceso directo para `bin = bin + 1`.
    
4. Para notificar el número de contenedor, el número de productos terminados en el contenedor y la suma acumulativa de productos terminados, escriba el código siguiente dentro del bloque de código `foreach`, después de `bin++;`:
    
    ```csharp
    Console.WriteLine($"Bin {bin} = {items} items (Running total: {sum})");
    ```
    
    Este código usará la variable del contador `bin`, la variable `foreach` temporal `items` y la variable `sum` para notificar el estado actual del inventario en un mensaje con un formato correcto.
    
5. Asegúrese de que el código coincide con lo siguiente:
    
    ```csharp
    int[] inventory = { 200, 450, 700, 175, 250 };
    int sum = 0;
    int bin = 0;
    foreach (int items in inventory)
    {
        sum += items;
        bin++;
        Console.WriteLine($"Bin {bin} = {items} items (Running total: {sum})");
    }
    Console.WriteLine($"We have {sum} items in inventory.");
    
    ```
    
6. Guarde los cambios en el archivo Program.cs y, a continuación, ejecute la aplicación.
    
    Debería ver la siguiente salida:
    
    ```
    Bin 1 = 200 items (Running total: 200)
    Bin 2 = 450 items (Running total: 650)
    Bin 3 = 700 items (Running total: 1350)
    Bin 4 = 175 items (Running total: 1525)
    Bin 5 = 250 items (Running total: 1775)
    We have 1775 items in inventory.
    
    ```
    

## **Resumen**

Estas son algunas cosas que debe recordar acerca de las instrucciones `foreach` y de los valores de incremento que ha aprendido en esta unidad:

- Use la instrucción `foreach` para recorrer en iteración cada elemento de una matriz y ejecutar el bloque de código asociado una vez por cada elemento de la matriz.
- La instrucción `foreach` establece el valor del elemento actual de la matriz en una variable temporal, la cual se puede usar en el cuerpo del bloque de código.
- Use el operador de incremento `++` para sumar 1 al valor actual de una variable.