### Comandos Bash.



### Comandos básicos del sistema de archivos (ls, cd, pwd).

ls: Poporciona una reprecentación visual de lo que hay en la carpeta.

ls -l: Lista archivos y directorios, en el directorioa actual, en un formato mas largo.
Puede incluir: permisos, números de enlaces, propietario, grupo, tamaño, fecha y hora de la ultima modificacion y nombre.

-- si ejecutas: -rw-r--r-- 1 usuario grupo  4096 feb  2 10:00 archivo.txt

-rw-r--r-- : Son los permisos (lectura y escritura para el propietario, solo lectura para el grupo y otros).

1 : Numero de enlaces duros.

usuario : Es el propietario.

grupo : Grupo al que pertenece el archivo.

4096 : Tamaño de bytes.

feb  2 10:00 : Fecha y hora de la ultiam modificación.

archivo.txt : Nombre del archivo.




cd(Change directory): Se utiliza para cambiar el directorio actual.


-- cd /ruta/al/directorio : Para cambiar a un directorio especifico.
-- Usando ~: Cambia rapidamente al directorio de inicio.
-- cd .. : Para volver/subir un nivel.










pwd(Print Working Directory): Muestra el directorio actual.



### Creacion y eliminación de archivos y directorios (touch, mkdir, mr).


touch: Se usa para crear archivos nuevos y vacios, o para actualizar la marca de tiempo de archivos existentes.

-- Si el archivo especificado no existe, touch lo creara.


touch filename.txt : Creación de un nuevo archivo vacio.




mkdir(Make Directory): Se utiliza para crear directorios(carpetas) nuevos.


mkdir directory_name : Creacion de nuevo directorio(carpeta).


mkdir -p parent_directory/child_directory

mkdir : Comando para crear directorios(carpetas).
-p : Infica a mkdir que cree directorios padres si no existen.
parent_directory/child_directory : Ruta donde se desea crear el directorio, en este caso se creará el directorio 'child_directory', dentro de 'parent_directory'.






rm(Remove): Se utiliza para eliminar archivos o directorios.

rm filename.txt : Elimina el archivo.
rm -r directory_name : Elimina un directorio y su contenido(Precaución).
rm -rf directory_name : Fuerza la eliminación de un directorio y su contenido.






### Copiar y mover archivos(cp, mv).


cp(Copiar): Se utiliza para copiar archivos o directorios de una ubicación a otra.

cd file.txt /path/to/destination/ : Copia un archivo a un directorio diferente.

cd file1.txt file2.txt directory/ : Copia varios archivos en un directorio.

cd -r source_directory/ destination_directory/ : Copia un directorio y su contenido.

    -r : Opcion que significa recursivo, indica que debe copiar todo el contenido del directorio.

    source_directory/ : Directorio origen, es decir, el directorio que quieres copiar.
    
    destination_directory/ : Directorio destino, es decir, a donde quieres copiar el contenido del directorio fuente.




mv(Mover): Se utiliza para mover archivos o directorios de una ubicación a otra.

mv file.txt /path/to/destiantion/ : Mueve un archivo a un directivo diferente.

mv oldname.txt newname.txt : Cambia el nombre de un archivo.

mv source_directory/ destination_directory/ : Mover un directorio y su contenido.




### Visualización del contenido del archivo.


cat(Lectura de archivos): Se utiliza para concatenar y mostrar todo el contenido de un archivo en la terminal.

    cat archivo.txt : Muestra el contenido del archivo en la terminal.


less: Permite ver el contenido de un archivo, pantalla por pantalla.

    less archivo.txt : Permite ver el contenido del archivo, pagina por pagina.


more: Muestra archivos de texto de a una pantalla a la vez.

    more archivo.txt : Similar a 'less', pero con menos funciones, muestra el archivo
    pagina por pagina y solo permite desplazarse hacia adelante(no hacia atras, como 'less').





### Busqueda de texto mediante GREP.

GREP(Impresión de expresiones regulares globales): Se utiliza para buscar y extraer patrones de texto dentro de archivos.


grep [optiones] pattern [file]

pattern : Texto o expresión regular que desea buscar.
file(opcional) : Archivos en lso que desea realizar la busqueda, si no se especifica, leerá desde la entrada estándar.


grep "search_term" file.txt : busqueda básica de una palabra o expresión.

    grep "hola" documento.txt 

    grep buscara la palabra hola dentro del archivo documento.txt



grep -i "search_term" file.txt : Busqueda de una palabra sin distinguir entre mayúsculas y minúsculas.


grep -E 'pattern' file.txt

    grep -E 'hola+' file.txt

    -E : Habilita expresiónes regulares.
    'hola+': patron o expresó regular que desea buscar.
    file.txt : archivo o archivos en los que desea realizar la búsqueda.

    + : Infica que 'hola' debe aparecer una o mas veces consecutivas en cada linea.
    


grep -n "pattern" file.txt : Mostrar números de lineas con coincidencias.

    n : Muestra números de linea para cada linea coincidente en la salida.






### identificación de la información del archivo.


file(archivo): Se utiliza para determinar el tipo y formato de un archivo.

    file documento.txt

    Salida esperada: documento.txt ASCII text





### Gestión de usuarios y grupos(whoami, id, chmod, chown) 


whoami : Se utiliza para mostrar el nombre de usuario del usuario actual que a iniciado sesion en el sistema.


id : Se utiliza oara mostrar información detellada del usuario y del grupo, incluido el UID(ID de usuario), GID(ID de grupo) y membresias de grupo.



-- permisos de archivos(chmod, chown).


chmod : Se utiliza para cambiar los premisos de archivo, lo que premite especificar quien puede leer, escribir y ejecutar un archivo(funciona en archivos y directorios).

    chmod 755 archivo.txt
    755 es uan representación numerica de los premisos.

    755: Es una representación numérica de los permisos.
    7 (propietario): Permisos de lectura (4), escritura (2) y ejecución (1) → 4 + 2 + 1 = 7.
    5 (grupo): Permisos de lectura (4) y ejecución (1) → 4 + 1 = 5.
    5 (otros): Permisos de lectura (4) y ejecución (1) → 4 + 1 = 5.
    Asigna permisos de lectura, escritura y ejecución al propietario, y permisos de lectura y ejecución al grupo y otros usuarios para el archivo archivo.txt.

    ![Tabla de permisos](image.png)


chown : Se utiliza para cambiar el propietario y el grupo de un archivo.

    chown usuario:grupo archivo.txt

    usuario : Es el nuevo usuario.
    grupo : Es el nuevo grupo asignado al archivo
    archivo.txt : Es el archivo al que se le cambian el propietario y el grupo.





