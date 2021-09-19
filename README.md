# ShellManagement
Es un pequeno programa que muestra como se administra de forma sencilla un sistema Linux. 
Muestra funciones para principalmennte ver infromacion de usuarios, grupos, sistema y procesos.

## Autor
Edgar Alejandro Hernandez Albino

### 1. Manejo de archivos
Para este modulo, la idea es mostrar infromacion completa sobre un archivo, independientemente de su tipo. 
Esta infromacion debe ser visualmente etendible para cualquier usuario, entoces para mostrar cada uno de los 
campos se planteo una funcion que validara primero si el archivo existia, y de ser asi muestra los atrubitos del archivo.
Para mostrar cada una de las propiedades se ejecuta un comando y se va modificando cada salida para mostrar exactamente 
lo que se quiere y ni una cadena que no sea necesaria. Por ejemplo: 

    echo "Numero de ligas duras: "$(ls -lid $1 | cut -f3 -d" " 2>> errores.log)" "
    
El comando anterior, muestra las propiedades de un archivo, depues se usa un cut para obtener el tercer campo que en este caso 
representa el numero de ligas duras del archivo. 

### 2. Manejo de procesos

### 3. Monitoreo de usuarios

### 4. Infromacion de sistema
