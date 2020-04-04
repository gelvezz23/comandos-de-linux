

## Permisos con la terminal de linux

**La Administración de Servidores está a cargo de muchas tareas: instalar herramientas, mantener el sistema operativo actualizado, gestionar usuarios y permisos, monitorear los servicios y puertos abiertos del sistema, identificar amenazas y vulnerabilidades, entre muchas otras.**

**En esta ocasión vamos a estudiar cómo funcionan los usuarios y permisos de nuestros servidores y computadoras personales con Linux o Mac.**
**Permisos para Usuarios, Grupos y Super Usuarios**

**Nuestro trabajo consiste en limitar las acciones que pueden realizar los usuarios de nuestros sistemas. Debemos encargarnos de que los usuarios no tengan más permisos de los que deberían tener.**

    Todo lo que no está explícitamente permitido, debe estar explícitamente prohibido.

**Cuando hablamos de permisos no solo hablamos de usuarios individuales, también hablamos de grupos y super usuarios:**

**Los grupos de usuarios nos permiten darles los mismos permisos a diferentes usuarios. Todos los usuarios que pertenezcan al mismo grupo tendrán los mismos permisos. Así evitamos tener que darle los mismos permisos a cada usuario individualmente, uno por uno. Con solo cambiar los permisos del grupo cambiamos el permiso de todos los usuarios.**

**También están los super usuarios, la parte más alta de la pirámide, los que pueden hacer cualquier cosa. Lo ideal no es trabajar con este tipo de usuarios, ya que podrá activar procesos o realizar tareas que afecten nuestro servidor o generar vulnerabilidades. Más bien, debemos crear usuarios para cada tarea en específico que realizamos en nuestros servidores.
Cómo funcionan los permisos**

**Cuando ejecutamos el comando ls podemos ver la lista de archivos y subcarpetas de la ruta donde nos encontramos. Si usamos este comando con la opción -lh podemos ver un poco más de información: fecha de modificación, peso, usuario propietario, grupo al que es miembro este archivo y los permisos.**

**Concentrémonos en la primera parte, la de los permisos:**

**drwxrw-r-- usuario grupo**    
**drwx------ usuario grupo**    
**-rwxr-xr-x usuario grupo**    
**-rwx------ usuario grupo**    

**La primera letra puede ser una d para indicar que hablamos de una subcarpeta o un guion (-) cuando evaluamos archivos.**

**Las siguientes 9 letras debemos dividirlas en grupos de 3. El primer grupo son los permisos del usuario propietario del archivo. El segundo son los permisos del grupo al que pertenece el archivo. Y el tercero son los permisos para cualquier otro usuario del sistema operativo.**

**Cada grupo de 3 puede comenzar con la letra r, refiriéndose a los permisos de lectura., continuar con w para referirse a los permisos de escritura y terminar con una x para indicar los permisos de ejecución.**

**Si en vez de estas letras encuentras un guion (-) significa que no ese usuario o grupo de usuarios no tienen ese tipo de permisos.**

**Veámoslo más claro con un ejemplo:**

**Estos son los permisos: -rwxr-xr-- juandc estudiantes-platzi.**

    Estamos trabajando con un archivo.

    El usuario propietario es juandc.

    Este archivo pertenece al grupo de estudiantes-platzi.

    El usuario propietario (juandc) tiene permiso para todo: leer, escribir y ejecutar el archivo.

    El grupo al que pertenece el archivo solo tiene permisos para leer y ejecutar el archivo, no para editarlo.

    El resto de usuarios de sistema operativo solo tienen permisos para leer el archivo, no para escribirlo ni ejecutarlo.

**(d|-) Carpeta o archivo.**

**(r|-) El usuario propietario del archivo tiene permisos de lectura.** 
**(w|-) El usuario propietario del archivo tiene permisos de escritura.**   
**(x|-) El usuario propietario del archivo tiene permisos de ejecución.**    

**(r|-) El grupo al que pertenece el archivo tiene permisos de lectura.**      
**(w|-) El grupo al que pertenece el archivo tiene permisos de escritura.**  
**(x|-) El grupo al que pertenece el archivo tiene permisos de ejecución.**  

**(r|-) Todo el resto de usuarios del S.O tienen permisos de lectura.**  
**(w|-) Todo el resto de usuarios del S.O tienen permisos de escritura.**      
**(x|-) Todo el resto de usuarios del S.O tienen permisos de ejecución.**      

**Actualización de permisos y propietarios**

**Bueno, ya sabemos leer los permisos, pero nos hace falta poder cambiarlos. Y para esto vamos a usar los comandos chmod y chown.**

**Cuando nos refiramos al usuario propietario debemos usar la letra u. Si cambiamos los permisos del grupo una g. Si queremos cambiar los permisos de cualquier otro usuario usamos la o. Y si queremos cambiar los permisos de TODOS usamos la a.**

## **Añadir permisos de escritura al grupo:**
    chmod g+w archivo.txt

## **Eliminar permisos de lectura a los usuarios no propietarios**
## **ni miembros del grupo al que pertenece el archivo:**
    chmod o-r

## **Añadir permisos de ejecución a todos (cualquier usuario):**
> **chmod a+x archivo.txt**

**Pero no solo podemos representar los permisos usando letras, también podemos hacerlo en formato numérico, con 3 números del 0 al 7:**

    - = 0
    x = 1
    w = 2
    r = 4

**Debemos sumar las 3 letras de cada permiso para obtener el “número definitivo”. Así que, continuando con el ejemplo anterior:**

    Permisos del usuario propietario: r (4) + w (2) + x (1) = 7.
    Permisos del grupo al que pertenece el archivo: r (4) + x (1) = 5.
    Permisos del grupo al que pertenece el archivo: r (4) = 4.

**Todo esto para un conseguir un resultado de 754. Así que, si queremos eliminar los permisos de ejecución para el grupo, podemos usar el comando chmod con el número 744.**

> **chmod 744 archivo.txt**

**Ahora digamos que queremos cambiar el usuario propietario de nuestro archivo. Para esto usaremos el comando chown seguido del nuevo usuario o grupo propietario del archivo.**

## **Cambiar el usuario propietario:
    sudo chown nuevo-usuario archivo.txt

## Cambiar el grupo propietario:
    sudo chown :nuevo-grupo archivo.txt

## Cambiar el usuario y grupo propietario:
    sudo chown nuevo-usuario:nuevo-grupo archivo.txt

## Conclusiones

La gestión de usuarios y permisos es solo una de todas las tareas que debemos realizar en la administración de servidores.