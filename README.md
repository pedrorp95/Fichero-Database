La primera parte de la practica consiste en tratar 3 ficheros de texto y generar un listado (nuevo fichero) de personas.
Los ficheros de entrada son:
Hombres: Nombres españoles de varones
Mujeres: Nombres españoles de mujeres
Apellidos: Apellidos españoles

Se trata de generar un numero de personas (no menor a 2000) con nombres aleatorios compuestos por nombre y dos apellidos
El numero de mujeres y hombres, tiene que estar en torno al 55%-45% respectivamente, siendo un factor a considerar en la 
generación de cada una de las personas

Para cada persona, se generará ademas de su nombre y apellidos (junto al sexo), la fecha de nacimiento y su codigo 
(C+numero, todos con la misma longitud de caracteres ) 


Los datos configurables deben estar asignados en un archivo de configuracion, en la misma ruta que vuestro programa
miprograma.conf
Y deberá contener, cualquier dato susceptible de variación:
fnombremujer = fic1 (siendo fic 1 el nombre del fichero con nombres de mujer)
Idem con el de hombres, el de apellidos y el fichero de salida
numpersonas=x (siendo x un numero no menor a 2000)
hombre=y (siendo y el % estimado de hombres)
minedad=minima edad posible
maxedad=maxima edad poisble


EL NOMBRE DE TODOS LOS FICHEROS DE SALIDA DEBE CONTENER EL NOMBRE DEL ALUMNO 
Deberemos obtener 2 ficheros de salida:
Personas:
Codigo;Nombre;Apellidos;Fecha Nacimiento

Resultado: Debe contener la siguiente información
Tiempos de procesos
Numero exacto y porcentajes de hombres y mujeres
10 mujeres más jovenes ordendas alfabeticamente por sus apellidos

--------------------------------------------------------------------------------------------
La segunda parte de la practica consiste en leer (de momento) un archivo binario que contiene
informacion de un catalogo de productos (productos.dat).

Codigo: Tipo entero
Descripcion: Maximo de 100 caracteres
Familia: Maximo de 8 caracteres
Precio: Tipo double
Marca de valido: Byte con posibles valores 0, 1 o 2

Hay que crear un programa que devuelva los registros de los productos que esten marcados con un valor 2 en su marca de valido
El programa solo debe recuperar la informacion completa (en sus respectivos campos) de los registros que cumplen la marca indicada
--------------------------------------------------------------------------------------------
La tercera parte de la practica consiste en leer, consultar y manipular(pendiente) datos de una base de datos

Lo primero es preparar una base de datos con suficiente contenido.
Contaremos con tres tablas:
- CLIENTES (codigo, nombre, apellidos, fecha nacimiento y sexo)
- ARTICULOS (codigo, nombre, familia, precio)
- VENTAS (idventa, fecha, codcliente, codproducto, cantidad, precio unitario)

1) Crear las tablas con todos sus campos, claves, etc
No es necesario hacerlo desde java.
Se puede usar codigo sql directamente en la herramienta de administracion de la BBDD
Se recomienda guardar dicho codigo por si es preciso reutilizarlo

2) Incoporar registros en las tablas maestras. Esta parte hay que hacerla en java
con lectura de ficheros (binarios y texto) y conexiones a base de datos y statement

- ARTICULOS:
Se debe llenar a partir del fichero binario (productos.dat). Reutilizar la segunda parte
de la practica, pero quedadonos con los produtos con la marca de valido=1

-CLIENTES:
Partidendo del fichero de personas generado en la primera parte de la practica,
incorporar todos las personas a la tabla de clientes.

- VENTAS:
Generar registros de ventas:
Idventa: Contador secuencial
Fecha: Debe ser una fecha no inferior al 1/1/2019 y no mayor que la fecha actual
Cada venta, tendra la fecha del dia anterior o hasta 2 despues despues.
Por ejemplo si la uttima venta generada es el 3-1-2019, la siguiente venta podrá ser 3, 4 o 5 de enero del 2019.
La ultima venta será la que ocurra el 1 de junio de 2021.
Cliente: Se obtendrá el codigo de forma aleatoria de entre los existentes en la tabla de CLIENTES
Producto: Se obtendrá el codigo de forma aleatoria de entre los existentes en la tabla de ARTICULOS
Precio: Se cogerá el precio que corresponde al articulo


En el fichero de resultados se debe incoporar, de momento, los resultados obtenidos por consultas lanzadas desde el programa
Numero de ventas generadas
Cantidad de clientes nacidos un 29 de febrero.
Mes y dia (independientemente del año) y cantidad de personas, con menor numero de personas nacidas.
Mes y dia (independientemente del año) y cantidad de personas, con mayor numero de personas nacidas.
Dia de mayor (euros) ventas junto con el detalle de la mismas


Otras funcionalidades:
Solicitar un codigo de cliente y mostrar sus datos y las compras realizadas.
Solicitar un codigo de producto y mostrar las ventas que ha tenido.

ULTIMA PARTE:
FUNCIONALIDAD para actualizar Productos:
Alta de producto
Modificación de descripción y/o precio de un producto
Eliminación de productos. Solo se podrá eliminar si no tienen ninguna venta

FUNCIONALIDAD de nueva venta:
Fecha de venta = a la fecha del sistema
Se solicitará codigo de cliente o 0=nuevo cliente,
en cuyo caso se debe proceder a la solicitud de todos sus datos para el nuevo cliente,
(Comprobar la posible coincidencia de todos los datos con un cliente ya existente, y en ese caso pedir confirmación)
Se solicitará:
- el codigo de producto, mostrandose su descripción y precio
- La cantidad
Se mostrará el importe de la venta, y se procederá a grabar la venta (y el nuevo cliente si es el caso) mediante transacción.
