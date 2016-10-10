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

-- Para mostrar todos los archivos que empiecen con la letra "j" en el directorio /usr/bin ejecutamos la siguiente línea de comandos por consola.

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

-- Para cambiar el nombre del directorio test/ a test2/ utilizamos el siguiente comando.

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

