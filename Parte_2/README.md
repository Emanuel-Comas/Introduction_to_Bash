### Introducción a la ordenación.


-- El comando 'sort' en sistemas Unix y similares se utiliza para organizar las lineas de archivos de texto o flujos de entrada en un orden especifico, su principal función es realizar operaciónes de ordenación, 'sort' se
puede aplicar a varios tipos de datos, incluidos númericos y textuales.




### Sintaxis básica de SORT.

Ordenación preterminada:

    sort names.txt

    -- Realiza una clasificación organizando las lineas alfabéticamente para los archivos de texto.

    
    sort names.txt > sorted_names.txt

    -- Crea el archivo 'sorted_names.txt' con las lineas de 'names.txt' ordenadas alfabéticamente.




Ordenación númerica:

    sort -n numbers.txt

    -n : Habilita la ordenación númerica en arden ascendente, conciderando los valores como números en 
    lugar de cadenas.

    sort -nr numbers.txt

    -nr : Ordena los números en orden descendente.

    sort -n numbers.txt > sorted_numbers.txt

    -- Crea un archivo llamado 'sorted_numbers' con los números ordenados númericamente.




Ordenación inversa:

    sort -r data.txt

    -r : Invierte el orden de clasificación.


    sort data.txt > sorted_data.txt

    -- Crea un archivo 'sorted_data.txt' con las lineas de 'data.txt' ordenadas en orden descendiente.




Ordenación basada en campos:

    sort -t':' -k2,2 file.csv

    -- Este comando ordena un archivo CSV según el segundo campo.

    -t':' : Le indica a sort que el delimitador entre campos es el carácter ':'.

    -k2,2 : Le indica a sort que debe ordenar el archivo usando solo la segunda columna(campo), 
    significa 'ordenar por el campo 2 y solo el campo 2'.

    file.csv : Es el archivo que quieres ordenar.



-- Si tienes un archivo 'file.csv' con el siguiente contenido:


![alt text](image.png)


-- El comando: 

    sort -t':' -k2,2 file.csv

-- Ordena las lineas según la segunda columna(edad), la salida es:


![alt text](image-1.png)


-- Para ordenar en orden descendente, se agrega '-r'

    sort -t':' -k2,2 -r file.csv




Ordenación única:

    sort -u names.txt

    -u : Elimina lineas duplicadas durante la ordenación.




-- Si tienes un archivo 'names.txt' con el siguiente contenido:


![alt text](image-2.png)


-- El comando:

    sprt -u names.txt


-- Ordena las lineas alfabéticamente y elimina las duplicadas, la salida seria:


![alt text](image-3.png)


-- Para guardar el resutlado en un nuevo archivo.

    sort -u names.txt > unique_names.txt

    -- Crea el archivo 'unique_names.txt' con las lineas ordenadas y sin duplicados.





Ordenación legible por humanos:

    sort -h sizes.txt

    -h : Realiza una clasificación legible para humanos, ej: 1k(kilobytes), 2m(megabytes).



-- Si tienes un archivo 'sizes.txt', con el siguiente contenido:


![alt text](image-4.png)


-- El comando:

    sort -h sizes.txt


-- Ordena los tamaños de manor a mayor, teniendo en cuenta las unidades, y el resutlado seria algo como:


![alt text](image-5.png)



-- Para guardar el resultado en u narchivo nuevo:

    sort -h sizes.txt > sorted_sizes.txt






Delimitador personalizado:

    sort -t'|' data.txt

    -t'|' : especifica un delimitador personalizado para los campos, ordena un archivo con '|' como 
    delimitador de campo, es decir, especifica el delimitador que se usara para separar las columnas.



-- Si tienes u narchivo 'data.txt' con el siguiente contenido, donde las columnas estan separadas por '|':


![alt text](image-6.png)


-- El comando:

    sort -t'|' data.txt


-- Ordena el archivo alfabéticamente por la priemra columna(en este caso, por los nombres), la salida seria:



![alt text](image-7.png)



-- Con la opción '-k', indica que columna utilizar para ordenar.

    sort -t'|' -k2,2 data.txt


-- Ordena el archivo 'data.txt' por la segunda columna(edad) en orden ascendente.


-- Para ordenar el resultado en orden descendente se agrega la opción '-r':

    sort -t'|' -k2,2 -r data.txt

-- Se ordenan los datos por la segunda columna en orden descendente.





### Introducción a UNIQ.