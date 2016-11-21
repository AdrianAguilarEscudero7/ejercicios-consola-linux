# ejercicios-consola-linux
Ejercicios de la consola de Linux

## Ejercicio01
· *Show all the jpg pictures in the current directory.*

-- Para mostrar todas las imágenes en el directorio /Imágenes por ejemplo, ejecutamos la siguiente línea de comandos por consola.

```console
ls Imágenes/*.jpg
```

## Ejercicio02
· *Display all the files in the directory /usr/bin starting with letter “j”.*

-- Para mostrar todos los archivos que empiecen con la letra "j" en el directorio /usr/bin, ejecutamos la siguiente línea de comandos por consola.

```console
ls /usr/bin/j*
```

## Ejercicio03
· *Show all the files in the directory /usr/bin starting with the letter “k”, with an “a” in the 3rd place.*

-- Para mostrar todos los archivos en el directorio /usr/bin que empiecen por la letra "k" y contengan una "a" en el tercer lugar, ejecutamos la siguiente línea de comandos por consola.

```console
ls /usr/bin/k?a*
```

## Ejercicio04
· *Show all the files in the directory /bin ending with “n”.*

-- Para mostrar todos los archivos del directorio /bin que acaben en "n", mostramos la siguiente línea de comandos por consola. 

```console
ls /bin/*n
```

## Ejercicio05
· *Display all the files in the directory /etc and all the files in every subdirectory recursively.*

-- Para mostrar todos los archivos en el directorio /etc y todos los archivos en cada subdirectorio recursivamente, ejecutamos la siguiente línea de comandos por consola.

```console
ls -R /etc/
```

## Ejercicio06
· *In your home directory, create another directory named test. Copy the file gzip from the directory /bin to test. Create a duplicate of gzip named gzip2 inside test.*

-- Para crear en el directorio /home un directorio llamado "test", ejecutamos la siguiente línea de comandos.

```console
mkdir test
```

-- Luego copiamos el archivo "gzip" desde el directorio /bin al directorio test/.

```console
cp /bin/gzip test/
```

-- Y para duplicarlo dento de test/ podemos ejecutar lo siguiente.

```console
cp test/gzip test/gzip2
```

## Ejercicio07
· *Change the name of the directory test to test2. Create test3 at the same level in the directory tree as test2 and move all the files from test2 to test3. Delete test2.*

-- Para cambiar el nombre del directorio test/, a test2/, utilizamos el siguiente comando.

```console
mv test/ test2/
```

-- Creamos el directorio test3/ en el mismo nivel que test2/ y movemos todos los archivos de test2/ a test3/

```console
mkdir test3/
mv test2/* test3/
```

-- Ahora borramos test2/

```console
rmdir test2/
```

## Ejercicio08
· *Create an empty file named “*?Hello all?*”. Can you? Is it a good idea to name a file this way? Explain your answer.*

-- Se puede crear, pero se crean 2 archivos por separado, además no es una buena idea nombrar de esta forma a los archivos, ya que "*" y "?", son ejemplos de comodines y se usan para relacionar caracteres con otras combinaciones de caracteres, ya sea de forma múltiple o individual. Su empleo más común es abarcar un número más amplio de archivos o directorios.


## Ejercicio09
· *Create a directory named multimedia_test and copy all the content from the directory multimedia into it. Then, create two files in multimedia/video/, one named films.txt and another named actors.txt. Edit the file films.txt and write the title of your favourite movie. Then, create another file in multimedia_test/video/, also named films.txt. Edit this file and now write the titles of your five favourite movies. Copy of all the content of multimedia into multimedia_test ensuring that only most recently modified versions of files remain.To check that everything is ok, check if multimedia_test/video contains the empty file actors.txt and the file films.txt contains 5 titles and not 1.*

-- Para crear un directorio llamado multimedia_test/ y copiar todo el contenido desde el directorio multimedia/ dentro de él, ejecutamos los siguientes comandos.

```console
mkdir multimedia_test/
cp -R multimedia/* multimedia_test/
```

-- Ahora creamos los dos archivos, "films.txt" y "actors.txt" en el directorio multimedia/video/, y editamos el archivo "films.txt" con gedit por ejemplo.

```console
cd multimedia/video/
touch films.txt actors.txt
gedit films.txt
```

-- A continuación creamos otro archivo en el directorio multimedia_test/video/, también llamado "films.txt" y lo editamos de manera diferente al otro.

```console
cd ../..
cd multimedia_test/video/
touch films.txt
gedit films.txt
```

-- Finalmente copiamos todo el contenido del directorio multimedia/ dentro del directorio multimedia_test/, asegurándonos de que no se copien los archivos que estén más desactualizados que los de la ruta destino.

```console
cd ../.. 
cp -R -u multimedia/* multimedia_test/
```

## Ejercicio10
· *Delete the directory multimedia/pictures/others. The system must ask for confirmation.*

-- Para borrar el directorio multimedia/pictures/other ejecutamos el siguiente comando.

```console
rmdir multimedia/pictures/other
```

-- Borrado con éxito, el sistema no preguntó confirmación.

## Ejercicio11
· *Move the file films.txt, which is in multimedia/video, to the directory above, at the same time renaming the file to my_films.txt.*

-- Para mover el archivo "films.txt" del directorio multimedia/video al directorio superior, renombrándolo al mismo tiempo a "my_films.txt", ejecutamos la siguiente línea de comandos por consola.

```console
mv multimedia/video/films.txt multimedia/my_films.txt
```
