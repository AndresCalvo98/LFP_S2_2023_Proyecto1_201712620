# LFP_S2_2023_Practica_201712620
# Práctica 1 - Lenguajes Formales y de Programación  

### Universidad de San Carlos de Guatemala
### Facultad de Ingeniería
### Escuela de Ciencias y Sistemas
### Lenguajes Formales y de Programación

<img src='https://user-images.githubusercontent.com/36779113/128587817-1a6c2fdc-d106-4dd3-b092-104c8299bded.png' background='white'>

> Nombre
> - Luis Andres Calvo Arreaga         201712620




Este programa en Python es un sistema de gestión de inventario que permite a los usuarios realizar diversas operaciones relacionadas con la administración de productos y sus movimientos. El programa ofrece un menú principal con las siguientes opciones:

Cargar Inventario Inicial: Permite cargar información sobre productos, cantidades, precios unitarios y ubicaciones desde un archivo. Estos datos se almacenan en una estructura de datos llamada inventario.

Cargar Instrucciones de Movimientos: Lee un archivo que contiene instrucciones para agregar stock a los productos existentes o vender productos. Las operaciones de agregar stock y vender productos se aplican al inventario según las reglas especificadas en el enunciado.

Crear Informe de Inventario: Genera un archivo de texto con un informe detallado del estado actual del inventario. El informe muestra una tabla con información sobre cada producto, incluyendo su nombre, cantidad, precio unitario, valor total y ubicación.

Salir: Termina el programa.

El programa utiliza funciones para llevar a cabo las operaciones mencionadas. Los datos del inventario se almacenan en un diccionario, donde cada producto se representa como una clave con su información correspondiente como valores. El programa interactúa con el usuario mostrando el menú principal y solicitando la entrada correspondiente para ejecutar las diferentes opciones.

En el menú principal y las diferentes funciones que realizan operaciones, se utilizan principalmente bucles while y estructuras de control if-else para manejar la interacción con el usuario y llevar a cabo las diferentes tareas.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Practica_201712620/assets/66381259/3fed446a-6fe5-42a5-8d0c-6c41b1213780)

### Función para cargar el inventario inicial
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Practica_201712620/assets/66381259/4f7726b7-b3e2-4c25-9ecb-b96d4ecf7e14)

### Función para cargar los movimientos del inventario
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Practica_201712620/assets/66381259/20390133-52d2-4ab9-81f9-88ab13f4e111)

### Función para crear el informe del inventario
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Practica_201712620/assets/66381259/e9abdc51-ad09-4955-9734-91057c6d5191)

### Función Carga de Inventario:
La función "Carga de Inventario" se encarga de leer un archivo con instrucciones de configuración inicial de productos y cargar esta información en una estructura de datos en memoria, en este caso, un diccionario. Estas instrucciones provienen del archivo ".inv" y tienen un formato específico.

La función "Carga de Inventario" recibe el nombre del archivo ".inv" como argumento y realiza las siguientes acciones:

Abre el archivo en modo lectura.
Lee cada línea del archivo y divide la línea en sus componentes utilizando el separador ;.
Para cada línea, crea una entrada en el diccionario del inventario con el nombre del producto como clave y una tupla que contiene la cantidad, el precio unitario y la ubicación como valor.
El resultado es que después de cargar el archivo, el inventario estará representado como un diccionario donde cada producto tiene su información asociada. Por ejemplo:

inventario = {
    'Manzanas': (100, 2.50, 'BodegaA'),
    'Peras': (50, 3.00, 'BodegaB'),
    'Platanos': (75, 1.75, 'BodegaC'),
    # ...
}
Esta función prepara el inventario con los productos y cantidades iniciales especificadas en el archivo para su uso posterior en otras operaciones del programa.

### Función Carga de Movimientos:
La función "Carga de Movimientos" se encarga de leer un archivo con instrucciones de movimientos de productos y actualizar el inventario en función de esas instrucciones. Estas instrucciones provienen del archivo ".mov" y pueden ser de dos tipos: agregar stock o vender producto. 
La función "Carga de Movimientos" recibe el nombre del archivo ".mov" como argumento y realiza las siguientes acciones:

Abre el archivo en modo lectura.
Lee cada línea del archivo y divide la línea en sus componentes utilizando el separador ;.
Según el tipo de operación (agregar stock o vender producto), realiza las siguientes acciones:
Para agregar stock:
Si el producto existe en la ubicación, actualiza la cantidad sumándole la cantidad especificada.
Si el producto no existe en la ubicación, muestra un mensaje de error.
Para vender producto:
Si el producto existe en la ubicación y la cantidad a vender es menor o igual que la existencia, actualiza la cantidad restando la cantidad especificada.
Si el producto no existe en la ubicación, muestra un mensaje de error.
Si la cantidad a vender es mayor a la cantidad en esa ubicación, muestra un mensaje de error.
### Función Crear Informe:
La función "Crear Informe" se encarga de generar un informe detallado del estado actual del inventario y escribirlo en un archivo de texto. El informe contiene información sobre todos los productos existentes en el sistema, incluyendo detalles como el nombre del producto, la cantidad disponible, el precio unitario, el valor total del inventario para cada producto y la ubicación del producto.

La función "Crear Informe" toma como argumento el nombre del archivo en el cual se escribirá el informe. A continuación, realiza las siguientes acciones:

Abre el archivo en modo escritura.
Escribe una línea de encabezado que contiene los nombres de las columnas del informe, separados por tabulaciones o espacios, para que el informe quede formateado en forma de tabla.
Itera sobre la lista de productos en el inventario y para cada producto, escribe una línea en el archivo que contiene la información detallada:
Nombre del producto.
Cantidad actual de unidades disponibles.
Precio unitario del producto.
Valor total del inventario para ese producto (calculado como cantidad disponible * precio unitario).
Ubicación del producto.
Después de recorrer todos los productos y escribir la información correspondiente en el archivo, la función cierra el archivo.

### Clases Utilizadas
 las clases en el programa son utilizadas para representar objetos y estructurar los datos de manera más organizada y modular. En este caso, se han creado dos clases: Producto y Inventario.

Clase Producto:
Esta clase se utiliza para representar un producto en el inventario. Cada producto tiene atributos como su nombre, cantidad, precio unitario y ubicación. La clase Producto se utiliza para crear objetos individuales que contienen esta información y facilitan el manejo de los productos en el programa.

Clase Inventario:
La clase Inventario se utiliza para representar el inventario en su conjunto. Tiene una lista de objetos de la clase Producto, lo que permite mantener un registro de todos los productos presentes en el inventario y sus respectivas cantidades, precios y ubicaciones. Además, esta clase contiene métodos para agregar, actualizar y buscar productos en el inventario.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Practica_201712620/assets/66381259/a5471a98-37a4-4cbb-933d-e5410887538f)

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Practica_201712620/assets/66381259/a5627a07-d356-474f-94c9-b5e0fdaa70b3)
