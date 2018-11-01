## Terminal Linux

La mayoría de los usuarios prefieren interactuar con el sistema a través de la interfaz gráfica, pero esta presenta muchas limitaciones cuando el asunto es cambios que el usuario podrá realizar en el sistema. Para el usuario salir de esa limitación y tener el control total existe una poderosa herramienta llamada terminal, también conocido como línea de comandos o shell. El terminal de Linux permite al usuario realizar cambios avanzados en el sistema a través del acceso root cuando un usuario se convierte en root significa que pasa a ser superusuario o administrador del sistema.

Para quien nunca utilizó el terminal, al principio puede encontrarlo un poco intimidador pero después de que usted vaya practicando se dará cuenta de que es más eficiente y hasta más fácil de usar la interfaz gráfica (sí, usted encontrará esto).

A continuación veremos una lista de comandos básicos y usuarios que son muy utilizados no sólo por aquellos que llegaron en el mundo del linux, sino también por usuarios experimentados.

(Antes de comenzar, puede abrir el terminal utilizando el acceso directo CTRL + ALT + T o puede buscar por terminal en dash)

#### man
El comando man debería estar en la parte superior de toda la lista de comandos importantes de Linux. La razón es muy simple: basta con ejecutarlo para cargar una página de manual (man page) sobre los comandos del sistema, con definiciones no sólo del uso de cada herramienta, sino también descripciones detalladas de los numerosos parámetros del software y ejemplos de uso.

Para leer las man pages es muy fácil y basta ejecutar el man siguiendo el nombre del comando que desea buscar ayuda. No olvide presionar la tecla Enter después de escribir el comando, de lo contrario no se ejecutará.

```
man cp
```

Al ejecutar el comando anterior, podrá leer todas las instrucciones para el uso del comando cp.


#### ls
Para listar los archivos existentes en algún directorio, basta con usar el comando ls. Si se ejecuta sin parámetros, enumerará el contenido del directorio en el que se encuentra, pero puede indicar una ruta para él.

```
ls / usr / local / bin
```
También puede utilizar ls para comprobar el tamaño y la fecha de creación de cada archivo o carpeta. Para ello, utilice el parámetro -l y si también desea listar los archivos ocultos, que empiezan con un punto, utilice:

```
ls -lha / usr / local / bin
```

#### cd
Para saltar de carpeta en carpeta, no es necesario abrir el gestor de archivos. En el propio terminal es posible navegar por el sistema de archivos usando el comando cd seguido del mismo.

la ruta que desea seguir.
```
cd / usr / local
```

Vale la pena notar que hay algunos atajos que pueden facilitar la vida del usuario. Si ejecuta el comando cd sin parámetros, se devuelve a la carpeta de usuario, ubicada en / home. Para volver un nivel arriba en el árbol de directorios, utilice:

```
cd ..
```

De esta manera, si usted está en / usr / local y ejecutar "cd ..", volverá al directorio / usr.

#### cp
Copiar un archivo por el terminal, utilice el comando cp siguiendo el archivo de origen y el destino para él, que puede ser una nueva carpeta cuando un nuevo archivo, con nombre diferente.

```
cp archivo1.txt y archivo2.txt
```

o entonces

```
cp archivo1.txt pastanova /
```

Para copiar un directorio completo, no se olvida de insertar el parámetro -r. Si desea clonar una carpeta, utilice:

```
cp -r carpeta1 carpeta2
```

#### mv
Para mover archivos existe el comando mv y se puede utilizar tanto para reubicar archivos como para cambiar el nombre de ellos. Si desea enviar el archivo de una carpeta a otra, simplemente utilice:

```
mv carpeta1 / archivo1 carpeta2 /
```

Si prefiere simplemente renombrarlo, utilice:

```
mv archivo1 archivo2
```

#### more
Si necesita leer el contenido de un archivo de texto, utilice el comando more seguido de la ruta y el nombre del archivo.

```
more /home/user/archivo.txt
```

Todo el contenido del archivo se mostrará en el terminal, rellenando la pantalla con texto. Para continuar con la lectura, presione la barra espaciadora y, si necesita volver una o más páginas, utilice la tecla "b". Si desea salir antes del final del archivo, pulse "q".

#### df
Para saber cuál es el espacio total y cuántos GB disponibles existen en cada partición del sistema, usamos:

```
df -h
```

La opción -h, por cierto, quiere decir human-readable, es decir, legible para los humanos. Si ejecuta el comando sin ella, la información se mostrará en kilobytes y será necesario convertirlas mentalmente a otras unidades.

#### sudo
Por razones de seguridad, Linux trabaja con permisos de usuario. Por eso, ciertos comandos o archivos son accesibles sólo por el propio dueño o por el usuario administrador (root). Para que no tenga que cambiar de usuario en todo momento, existe el comando sudo, que garantiza credenciales de usuario root temporalmente, mediante la información de una contraseña.

Para realizar la prueba, intente ejecutar el comando:

```
ls / root
```

Recibirá una advertencia de permiso denegada. A continuación, ejecute:

```
sudo ls / root
```

Después de informar la contraseña de su propio usuario (en el caso de Ubuntu), el comando se ejecutará normalmente y los archivos de la carpeta raíz aparecerán en el terminal.

#### grep
Imagine la situación siguiente: tiene un archivo de texto con alrededor de 200 nombres de alumnos de una escuela, pero no está seguro de si un nombre específico aparece. El grep le ayuda a buscar por ese alumno ya hacer mucho más con la ayuda de expresiones regulares. Si no está seguro de si el nombre del estudiante se ha escrito respetando las letras mayúsculas, agregue el parámetro -i para que grep pase a ignorar esta distinción durante la búsqueda.

```
grep isadora -i archivo.txt
```

#### clear
Por último, un comando que ayuda a organizar un poco la confusión de letras que quedan en el terminal después de horas de uso. Para borrar toda ella, ejecute el comando clear. Después, es sólo volver a usar el terminal normalmente, como si nada hubiera pasado.

```
clear
```
