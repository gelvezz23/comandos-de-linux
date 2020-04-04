Comandos para trabajar desde nuestra ubicación

Lista los archivos que se encuentran en el directorio sobre el que estamos trabajando:

> ls

Lista todos los archivos incluyendo aquellos que se han definido como ocultos:

> ls -a

Todos los directorios contienen los archivos . y .., estos son punteros a directorios.

.. --> directorio padre
. --> directorio actual

Otros parámetros que puedes usar con el comando ls:

Ordena los archivos por fecha de modificación:

> ls -t

Ordena los archivos por extensión:

> ls -x

Muestra toda la información: usuario, grupo, permisos, tamaño, fecha y hora de creación.

> ls -l

Muestra la misma información que ls -l pero con las unidades de tamaño en KB, MB:

> ls -lh

Muestra el contenido de todos los subdirectorios de forma recursiva:

> ls -R

Ordena los resultados por tamaño de archivo:

> ls -S

Comandos para cambiar de ubicación

Print Working Directory: se usa para mostrar el directorio actual en el que nos encontramos trabajando.

> pwd

cd: se utiliza para cambiar de directorio. Luego del comando se debe especificar la ruta del directorio al que nos queremos mover. Por ejemplo:

> cd /home/mi_usuarioR

Comandos para mover, copiar o borrar

cp: copiar un archivo hacia un directorio.

> cp [archivo que se va a copiar] [directorio hacia el que se va a mover]

rm: eliminar un archivo.

> rm archivo.txt

`mv``: mover un archivo, cambiar su ubicación. La sintaxis es así:

>mv [ruta del archivo] [directorio hacia el que se va a mover]

rmdir: eliminar un directorio. En este caso es importante resaltar que, para que el directorio pueda ser eliminado, no puede contener archivos u otros directorios en su interior.

> rmdir [ruta / nombre del directorio a eliminar]

¡Desafío!

El desafío de esta clase consiste en utilizar todos los comandos y recursos que estudiamos hasta ahora para organizar tu espacio de trabajo como desarrolladora.

    Ve a tu carpeta personal (/home/tunombre).
    Crea una carpeta llamada development y entra en ella.
    Crea una nueva carpeta con el nombre del próximo curso que vas a tomar en Platzi y entra en ella. Te recomiendo escribir los nombres de carpetas o archivos en minúsculas y no usar espacios ni tildes para evitar dificultades (por ejemplo: prog_basica o programacion-basica).
    ¡Ay, disculpa! Debíamos guardar las carpetas de los cursos en otro lugar. Mueve la carpeta de tu próximo curso a esta nueva ubicación: /home/tunombre/learning/tuproximocurso. Puedes mover la carpeta como prefieras, con el comando para mover directorios o los comandos de copiar y eliminar.

Cualquier duda o dificultad que te encuentres puedes dejarla en la sección de comentarios. Estaremos atentos para ayudarte.