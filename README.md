# ShellManagement
Es un pequeno programa que muestra como se administra de forma sencilla un sistema Linux. 
Muestra funciones para principalmennte ver infromacion de usuarios, grupos, sistema y procesos.

### Autor
Edgar Alejandro Hernandez Albino

## Funcionamiento del programa
Primero se muestra un menu, en donde el usuario sera capaz de elegir la informacion que desea ver, o los 
cambios que quiere hacer. 

    >> Ingresa la opcion que deseas: 5

    ---------------------------------------
    1. Manejo de archivos
    2. Manejo de procesos
    3. Manejo de usuarios
    4. Informción del sistema
    5. Salir
    ---------------------------------------

    > ¿Que deseas hacer?: 
    
Dependiendo del numero que elegia,  tendra a su diposicion diferentes menus y funciones.  Tanto el menu como
los submenus, son manejados por un ciclo while y para la eleccion de cada una de las opciones se tienen case
que realizaran operaciones orientadas a lo que se requiera. 

### 1. Manejo de archivos
Para este modulo,  la idea es mostrar infromacion completa sobre un archivo,  independientemente de su tipo. 
Esta infromacion debe ser visualmente etendible para cualquier usuario, entoces para mostrar cada uno de los 
campos se planteo una funcion que validara primero si el archivo existia, y de ser asi muestra los atrubitos 
del archivo.  Para mostrar cada una de las propiedades se ejecuta un comando y se va modificando cada salida 
para mostrar exactamente lo que se quiere y ni una cadena que no sea necesaria. Por ejemplo: 

    echo "Numero de ligas duras: "$(ls -lid $1 | cut -f3 -d" " 2>> errores.log)" "
    
El comando anterior, muestra las propiedades de un archivo, depues se usa un cut para obtener el tercer campo 
que en este caso representa el numero de ligas duras del archivo.  En caso de que el archivo exista y despues
de haber mostrado su infromacion, aparecera un submenu como el siguiente: 

    ----------------------
    -Elegiste la opcion 1-
    ----------------------
    **********************************************
    1. Modificar los permisos del archivo (modo octal)
    2. Borrar el archivo
    3. Regresar al menu principal
    **********************************************
    
    >>> Ingresa la opcion que deseas:
    
En este menu, se podran modificar los permisos del archivo o incluso borrarlo. 

### 2. Manejo de procesos

Para este modulo solo se tiene una sola expresion con comandos que lanza el resultado requerido.En el caso de 
que se requiera de informacion de procesos se tendra un submenu como el siguiente: 

    ----------------------
    -Elegiste la opcion 2-
    ----------------------
    **********************************************
    1. Listar la tabla de procesos 
    2. Listar la tabla de procesos de un usuario especıifico
    3. Matar un proceso
    4. Numero de procesos totales corriendo en el sistema
    5. Regresar al menu pricipal
    **********************************************

    >> Ingresa la opcion que deseas: 

Y dependiendo de la opcion elegida se tendra una salida similar a:

    OPCION 4
    El número de procesos totales es: 285 

### 3. Monitoreo de usuarios
Como en el primer modulo, se creo una funcion para mostrar la infromacion de un usuario especifico y aunque no se
reutilice codigo las funciones ayudan a leer de manera mas sencilla el archivo. El menu se muestra a continuacion:

    ----------------------
    -Elegiste la opcion 3-
    ----------------------
    **********************************************
    1. Mostrar información de un usuario especı́fico
    2. Número total de usuarios que existen en el sistema
    3. Número total de grupos que existen en el sistema
    4. Número y lista de los logines usuarios conectados al sistema
    5. Número y lista de los logines de usuarios que están ejecutando procesos en el sistema
    **********************************************

    >>> Ingresa la opcion que deseas:
    
Para el caso de de la primer opcion, primero se ingresa el usuario, y si existe nos da su informacion:
 
    OPCION 1
    Ingresa el UID o Login de usuario para ver su informacion: alejandro

    Login: alejandro 
    UID: 1000 
    Grupo: alejandro 
    Nombre: Alejandro,,, 
    HOME: /home/alejandro 
    SHELL: /bin/bash 
    
Las otras opciones solo muestran un salida sencilla de un comando: 

    OPCION 2
    El numero total de usuarios en el sistema es: 46 

### 4. Informacion del sistema
Finalmente, para el ultimo modulo se muestra directamente la infromacion del sistema, ya que aqui no se tiene un
menu de opciones: 

    ----------------------
    -Elegiste la opcion 4-
    ----------------------
    Hostname: disorder 
    Sistema Operativo: elementary OS 
    Arquitectura del sistema: x86_64 
