# LFP_S2_2023_Practica_201712620
# Práctica 1 - Lenguajes Formales y de Programación  

### Universidad de San Carlos de Guatemala
### Facultad de Ingeniería
### Escuela de Ciencias y Sistemas
### Lenguajes Formales y de Programación

<img src='https://user-images.githubusercontent.com/36779113/128587817-1a6c2fdc-d106-4dd3-b092-104c8299bded.png' background='white'>

> Nombre
> - Luis Andres Calvo Arreaga         201712620
# Manual Tecnico

La siguiente aplicacion fue creada en lenguaje Python haciendo uso de la librería de Tkinter y el Paradigma POO.
Esta se divide en varios segmentos, y comenzaremos visualizando el Analizador Lexico ya que es la parte mas importante.
<strong>la clase Analizar contiene lo siguiente:</strong>

<strong>Importaciones y definición de Token:</strong> Aquí importas algunas bibliotecas necesarias y defines un namedtuple llamado Token para representar tokens con un valor, línea y columna.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/5daaf3c2-05b8-4e4d-9cdf-23ac26f4526e)


<strong>Inicialización de variables globales:</strong> Estableces algunas variables globales como line, col, y tokens para rastrear la posición actual en el análisis léxico y almacenar los tokens encontrados.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/b89019f6-9840-4771-a846-bcab440d885e)


<strong>Diccionario de configuración:</strong> Creas un diccionario llamado configuracion para almacenar información relacionada con la configuración.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/a19e9d2b-48f9-4d8d-a874-ed4ff9e45b72)

<strong>Función tokenize_string:</strong> Esta función toma una cadena de entrada y un índice como entrada y tokeniza una cadena entre comillas dobles (un string) dentro de la entrada. Devuelve el token y la posición actual en la cadena.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/b946cedd-49aa-407a-888b-9cfce99d320d)


<strong>Función tokenize_number:</strong> Esta función toma una cadena de entrada y un índice como entrada y tokeniza un número (ya sea entero o decimal) dentro de la entrada. Devuelve el token y la posición actual en la cadena.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/bc11c7a8-77e0-4a3d-bb59-708cfe250c35)


<strong>Función tokenize_input:</strong> Esta función toma una cadena de entrada completa y la divide en tokens. Itera a través de la entrada, maneja espacios en blanco, cadenas, números y otros caracteres especiales.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/a9f5d104-5535-4cf6-9b4d-7bae2aa581b5)
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/a5d36dbb-9037-4c9a-a34b-c6d185cdd6cb)


<strong>Función get_instruccion:</strong> Esta función se utiliza para analizar los tokens generados y construir instrucciones. Las instrucciones están relacionadas con operaciones aritméticas y trigonométricas, así como configuraciones relacionadas con texto, fondo, fuente y forma. Devuelve un objeto que representa una instrucción.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/bf37c8cc-94d2-4043-949e-c96d0dac1dbc)
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/6d68d235-0287-47af-9434-adcfb1579113)


<strong>Función create_instructions:</strong> Utiliza get_instruccion para crear una lista de instrucciones a partir de los tokens generados. También agrega información de configuración al árbol. Devuelve una lista de instrucciones.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/68df207d-7645-4c32-ad1c-19786cdad63b)


<strong>Función analizar:</strong> Toma una cadena de entrada, tokeniza y analiza las instrucciones, y luego interpreta y muestra los resultados en la consola.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/f006a9f2-8b37-4163-870e-59edcb0a4620)


<strong>Función Analizar_op:</strong> Similar a analizar, pero muestra los resultados de las operaciones en una ventana emergente utilizando la biblioteca messagebox.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/467821e1-af35-4f90-9e72-c03ec29bf77e)


<strong>Función tokenize_input_reporte:</strong> Esta función es similar a tokenize_input, pero se utiliza para generar un informe de errores. A diferencia de tokenize_input, no agrega tokens a la lista tokens, sino que registra errores en un formato específico.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/bf025d4d-a13b-4ecb-a6f8-3b5bec2c80e4)
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/f8b7ca49-239e-4e77-8231-c372ac70d277)

### luego pasamos a la carpeta de expresiones
En esta encontraremos la clase abstracta <strong>expresion</strong>.
y sus 2 clases hijas que heredan de la ella misma.<strong>(aritmeticas, trigonometricas)</strong>

En la clase <strong>expresion</strong> defines la clase abstracta Expresion y la haces heredar de la clase ABC. Esto indica que Expresion es una clase abstracta y que se utilizará como base para definir otras clases que implementarán métodos específicos.

@abstractmethod: Este es un decorador que se utiliza justo antes de la definición de un método. Indica que el método decorado es abstracto y debe ser implementado por cualquier subclase de la clase Expresion. En este caso, el método abstracto se llama interpretar.

<strong>def interpretar(self, contexto):</strong> Este es el método abstracto que todas las subclases de Expresion deben implementar. Toma dos parámetros: self, que es una referencia al objeto en sí, y contexto, que es un objeto que generalmente se utiliza para almacenar información o estado necesario para la interpretación de la expresión. Sin embargo, la implementación concreta de este método dependerá de las subclases concretas que hereden de Expresion.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/f09b73a3-b8db-4346-811d-2af284bd68c2)

En la clase <strong>aritmeticas</strong>


La clase tiene un constructor __init__ que inicializa varios atributos, incluyendo el tipo de operación aritmética, los dos valores involucrados en la expresión, y la ubicación de la expresión en un código fuente.
Implementa un método interpretar que evalúa la expresión aritmética y devuelve su resultado.
Implementa un método __str__ que proporciona una representación en forma de cadena de la instancia de la clase.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/a12c4968-1a42-49eb-951e-5be51f67173d)
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/671596ca-8912-4d31-8432-604d9871d7a8)


<strong>Funcionalidad:</strong>

El método <strong>interpretar</strong> realiza los siguientes pasos:
Evalúa los valores de la expresión (valor1 y valor2), que pueden ser números o expresiones más complejas.
Realiza una operación aritmética específica (como suma, resta, multiplicación, etc.) según el tipo de operación especificado.
Grafica la expresión en un árbol junto con los nodos que representan los valores y la operación realizada.
Devuelve el resultado de la operación, redondeado a dos decimales, así como los valores originales de valor1 y valor2 y el tipo de operación realizada.
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/919d47b5-42ae-4460-8a4d-e1e35e699815)
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/71897c30-c134-4453-9379-a55c3b967150)
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/07b4f6ec-4220-43c4-a2cc-576bf60132e6)

En la clase <strong>trigonometricas</strong> tiene un constructor __init__ que inicializa varios atributos, incluyendo el tipo de operación trigonométrica, el valor sobre el cual se aplicará la operación, y la ubicación de la expresión en un código fuente.
Implementa un método interpretar que evalúa la expresión trigonométrica y devuelve su resultado.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/df80a9f7-0014-466c-b716-3a66d5236833)

<strong>Funcionalidad:</strong>
El método interpretar realiza los siguientes pasos:
Evalúa el valor sobre el cual se aplicará la operación (valor), que puede ser un número o una expresión más compleja.
Realiza una operación trigonométrica específica (como seno, coseno, tangente, inverso) según el tipo de operación especificado (self.tipo).
Grafica la expresión en un árbol junto con el nodo que representa el valor y la operación realizada.
Devuelve el resultado de la operación trigonométrica, redondeado a dos decimales.
Operaciones Trigonométricas:

La clase admite las siguientes operaciones trigonométricas: seno, coseno, tangente e inverso.
Dependiendo del tipo de operación, se utiliza la biblioteca math de Python para calcular el resultado correspondiente.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/1e228867-0d25-4888-8bf2-a8544ef93098)

### clase Arbol
<strong>Constructor (__init__):</strong>En el constructor, se inicializa la clase Arbol. Se crea un objeto graphviz.Digraph que se utilizará para representar y visualizar el árbol. El comentario del árbol incluye una marca de tiempo para identificarlo de manera única. Además, se inicializa un contador (self.counter) que se utiliza para generar nombres únicos de nodos.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/ce1fdbbd-ba7e-43ab-847c-30b6825fd1c9)

<strong>Método agregarConfiguracion:</strong> Este método se utiliza para configurar la apariencia de los nodos en el gráfico del árbol. Toma un diccionario llamado confg como entrada, que contiene información sobre el fondo, fuente y forma de los nodos. Luego, aplica estas configuraciones al objeto dot de graphviz para los nodos del árbol.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/26456f0c-cd42-467d-b804-4cb78555fe20)


<strong>Método agregarNodo:</strong> Este método agrega un nodo al gráfico del árbol. Toma un valor como entrada y genera un nombre único para el nodo (usando el contador) antes de agregarlo al gráfico. El valor se muestra en el nodo.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/b53e2ccb-196c-42ba-8e68-e979510a0769)

<strong>Método agregarArista:</strong> Este método agrega una arista entre dos nodos del árbol. Toma los nombres de los dos nodos como entrada y crea una conexión entre ellos en el gráfico del árbol.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/559d5dde-5164-4524-8522-e08a9cf3ab76)


<strong>Método generarGrafica:</strong> Este método genera y guarda la representación gráfica del árbol en un archivo. Utiliza el método render de graphviz para crear el gráfico en un archivo y luego lo muestra en la vista predeterminada del sistema. También guarda el archivo en formato .dot para su posterior referencia.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/d477c032-a1f3-47b0-a607-2bcfbf46302b)

<strong>Método obtenerUltimoNodo:</strong> Este método devuelve el nombre del último nodo creado en el árbol. Esto se logra utilizando el contador para generar el nombre del nodo.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/5168ee61-900c-44bb-9f5a-c9c536e52247)


<strong>Instancia de la clase Arbol:</strong> Al final del código, se crea una instancia de la clase Arbol llamada arbol. Esto se hace para que puedas utilizar esta instancia para crear y gestionar gráficos de árbol a lo largo de tu programa.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/1ab39086-9ce7-4e35-b8b8-c3f1913c85ae)

### Por ultimo pasamos a la intefaz grafica
### Clase Gui
<strong>ScrollText:</strong> Esta es una clase que hereda de tk.Frame y se utiliza para crear un área de texto con desplazamiento en la interfaz gráfica. Permite al usuario escribir y editar texto en un área que incluye números de línea en el lado izquierdo.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/553ef814-01dc-4468-93f0-a95cdfd0495d)
![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/100b1f70-0c8b-40c1-861f-a6798fa26f36)

<strong>TextLineNumbers:</strong> Esta es otra clase que hereda de tk.Canvas y se utiliza para mostrar los números de línea en el área de texto. Está vinculada al widget de texto y se encarga de dibujar los números de línea.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/af638c63-ab5c-48e7-8e53-d414db4b5cf4)


<strong>Ventana:</strong> Esta es la clase principal de la aplicación que hereda de tk.Tk. Define la ventana principal de la aplicación con un menú. Aquí están las características clave:

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/30b81920-caed-4f3b-adce-0ca9c19317dd)


La ventana principal se configura con un título y una geometría inicial.
Incluye un área de ScrollText que permite al usuario escribir y editar texto con desplazamiento y números de línea.
Hay un menú que permite al usuario abrir, guardar y realizar acciones específicas, como "Analizar" y "Ver reporte".
La función open_file permite al usuario abrir un archivo y cargar su contenido en el área de texto.
La función save_file permite al usuario guardar el contenido actual del área de texto en un archivo.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/8e908379-ef7b-43ef-9115-00d4c8c08620)

<strong>La función analizar_texto</strong> analiza el contenido del área de texto utilizando una función llamada analizar y muestra el resultado en un visor de gráficos (usando arbol.dot.view()).

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/2ca15dec-0e72-47d7-a942-b23e039fc1d2)


<strong>La función analisis_Operaciones</strong> realiza una operación específica (no proporcionada en el código) en el contenido del área de texto.
Inicialización de la Aplicación: Al final del código, se crea una instancia de la clase Ventana llamada app y se inicia el bucle principal de la aplicación (app.mainloop()).

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/997527e4-3b35-42a2-89a5-062568fe0494)


# Manual De Usuario
El siguiente programa es un Interfaz grafica emulando un editor de texto tal como se muetra en la siguiente imagen.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/1ad198b2-aa27-4138-ab9c-36ffd2a54b74)

Este cuenta con las siguientes opciones de menu en la esquina superior izquierda.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/b0ed3e78-4697-4e01-913f-0572d92e7db1)

<strong>File:</strong> Esta opcion desplega un menu mostrado a continuacion:

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/c6ce5c50-be47-4351-8468-d4bb65ef1db4)

En este encontraremos multiples opciones...

<strong>New:</strong> Deja el editor de texto vacio para que uno pueda crear un nuevo archivo.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/eebd7536-a315-41b0-941e-9ec004f30512)

<strong>Open:</strong> Este desplegara una ventana de buscador de archivos para poder abrir un archivo de texto en la intefaz grafica.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/94c60651-a212-4970-ae8b-a7a97825ef99)


![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/fffadb16-4879-4ffe-946c-e40c46f14426)

<strong>Save file:</strong> con esta opcion podremos guardar, desde un buscador de archivos, el texto escrito en la interfaz grafica y asignarle un nombre para almacenarlo en algun lugar del computador.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/d6d66c51-35ac-419f-af90-485447e06cf8)

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/c4ceac31-a8e8-427c-96a7-77c4c34a1935)

<strong>Exit:</strong> Esta opcion cierra por completo la aplicacion creada.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/43c018ab-518f-44f8-a364-a9de1505bb18)

### Funcionalidad sobre el analizador Lexico de un archivo Json con operaciones aritmeticas y trigonometricas

<strong>Esta seccion es bastante interesante, ya que para ver el funcionamiento de el mismo tenemos que tener claro ciertas cosas:</strong>
<strong>1.</strong> Solo permite las operaciones mostradas a continuacion y con la siguiente sintaxis:

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/ec7dd9b3-ec99-49ae-b9be-e4f54d7c2ce0)

<strong>2.</strong> Solo permite Archivos de tipo .Json para realizar el analisis y las operaciones.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/15e58372-fa67-4e28-a717-533c4dda1237)

<strong>3.</strong> Tienen que tener la siguiente estructura.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/9e672c66-027a-47b2-afa0-b5f6ccfecc48)

### Siguientes funciones de la barra de la esquina superior izquierda

<strong>Analizar:</strong> muestra los resultados de todas las operaciones contenidas en el archivo .Json Analizado

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/29122f9d-4576-4f13-ac25-32e6851c0094)

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/c3cf8a6a-245e-4bad-bead-33227d1d2c96)

<strong>Ver Reporte:</strong> Despliega un PDF en el visor predeterminado de imagenes del equipo utilizado, que contiene un grafo de los resultados y jerarquias de las operaciones analizadas del archivo .Json ingresado.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/2f1f2b98-cf66-4de1-a939-929bfb7d4ebe)

<strong>Ver Errores:</strong> muestra un archivo de salida .Json con los errores un dicha estructura y devueltos de la misma manera.

![image](https://github.com/AndresCalvo98/LFP_S2_2023_Proyecto1_201712620/assets/66381259/9de8b4b0-09d6-442d-9c3c-2a2e63a96a86)














<<<<<<< HEAD
### Manual De Usuario
El siguiente programa es un Interfaz grafica emulando un editor de texto tal como se muetra en la siguiente imagen.
![Alt text](image-2.png)
=======
>>>>>>> 1671f2dfd092a9438b19eb854466d38c5ba71add
