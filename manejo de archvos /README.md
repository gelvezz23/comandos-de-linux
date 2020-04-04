**Vamos a estudiar algunos comandos para procesar texto y emitir un resultado. Te recomiendo que no solo te quedes con la lectura, sino que experimentes todo lo que quieras con estos comandos, ya que más adelante los necesitarás para completar los desafíos.
Trabajo fundamental con archivos de texto**

**En clases anteriores estudiamos cómo crear y organizar nuestras carpetas. Ahora vamos a trabajar archivos que, por supuesto, debemos guardar en estos directorios que previamente creamos.**

**touch: nos permite crear archivos.**

> **touch archivo.txt**

**cat: nos permite visualizar todo el contenido de nuestros archivos.**

> **cat archivo.txt**

**head: es muy parecido al comando cat. También nos permite visualizar el contenido de nuestros archivos, pero debemos indicarle cuántas líneas nos debe mostrar. Por defecto nos mostrará las primeras 10.**

 **primeras 10 líneas**
> **head archivo.txt**

 **primeras 20 líneas**
> **head -n 20 archivo.txt**

**tail: funciona igual que el comando head, pero al revés. También debemos indicarle cuántas líneas nos debe mostrar, la diferencia es que no las mostrará de abajo hacia arriba. Por defecto nos mostrará las últimas 10.**

 **últimas 10 líneas**
> **tail archivo.txt**

 **últimas 5 líneas**
> **tail -n 5 archivo.txt**

**Búsqueda y tratamiento de texto**

**No solo podemos visualizar nuestros archivos (o parte de nuestros archivos) tal cual como escribimos, también podemos filtrar y cambiar el contenido que podemos ver en los archivos.**

**Por ejemplo: imagina que tenemos un archivo gigante, con cientos o incluso miles de líneas. Si imprimieramos el contenido de todo el archivo sería muy difícil encontrar el nombre de una persona o elemento específico.**

**Y se vuelve aún más complicado si necesitamos que las palabras que buscamos cumplan ciertas condiciones, como solo mayúsculas o minúsculas, que la siguiente o anterior palabra cumpla ciertas condiciones, etc.**

**En estos casos podemos utilizar el comando grep para filtrar las líneas que queremos visualizar utilizando (o no) expresiones regulares:**

**grep “palabra-clave” archivo_gigante.txt**

**Si nos da igual si la palabra clave incluye mayúsculas o minúsculas podemos utilizar el flag -i:**

**grep -i “pAlaBra-cLAvE” archivo_gigante.txt**

**También podemos verificar si la línea incluye esta palabra clave al final:**

**grep “palabra-clave$” archivo_gigante.txt**

**O si la incluye al principio:**

**grep “^palabra-clave” archivo_gigante.txt**

**También hay situaciones donde necesitamos modificar un poco la información que obtenemos de un archivo de texto.**

**Por ejemplo, imagina que nuestro archivo contiene un poema, frase o saludo para responderle a los usuarios de nuestra aplicación. El problema es que cada usuario tiene un nombre diferente.**

**¡Hola, NOMBRE_USUARIO! Felicitaciones por completar tu desafío con PUNTOS_USUARIO puntos.**

**No queremos editar este archivo. Solo necesitamos cambiar los caracteres NOMBRE_USUARIO por el verdadero nombre del usuario.**

**Para esto podemos utilizar el comando sed. Solo debemos indicarle que queremos realizar una sustitución (s/), la palabra que vamos a cambiar (NOMBRE_USUARIO), la nueva palabra que vamos a incluir (Ana) y cerrar con el símbolo /.**

> **sed ‘s/NOMBRE_USUARIO/Ana’ archivo-saludo.txt**

**Ahora imagina que, además del nombre, debemos cambiar también la puntuación que obtuvo el usuario:**

> **sed ‘s/NOMBRE_USUARIO/Ana/; s/PUNTOS_USUARIO/35/’ archivo-saludo.txt**

**Puedes ver muchos más usos del comando sed en este tutorial: https://likegeeks.com/es/sed-de-linux/.**

**youtube** : https://www.youtube.com/channel/UC4sY2EC2d9rgAeGSw7iwjbg/videos

**facebook** : https://www.facebook.com/groups/silux/

**twitter** : https://twitter.com/SiluxUfps