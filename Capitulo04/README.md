# ejercicios-consola-linux
Ejercicios de la consola de Linux

## Ejercicio01
· *Complete the following table:*

| 654 |           |    
|-----|-----------|
|     | rwxrw-rw- |
|     | rwxrwxrwx |
| 520 |           |
| 764 |           |
|     | r--r----- |

-------------------

| 654 | rw-rx-r-- |
|-----|-----------|
| 766 | rwxrw-rw- |
| 777 | rwxrwxrwx |
| 520 | r-x-w---- |
| 764 | rwxrw-r-- |
| 440 | r--r----- |


# In the following exercises, you should use the required Linux commands to perform the operations described.

## Ejercicio02
· *Create the groups office1 and office2.*

-- Se quiere crear los grupos office1 y office2, para crear los grupos debemos escribir la instrucción groupadd. Es fundamental realizar las instrucciones previamente como super-usuario, si no, dará error. Para ello escribiremos sudo antes de las instrucciones correspondientes.

```console
sudo groupadd office1
sudo groupadd office2
```

## Ejercicio03
· *Create the users gearoid and paul. These users must belong only to the group office1.*

-- Para crear los usuarios gearoid y paul, se utiliza la instrucción adduser, aunque para matar dos pájaros de un tiro, podemos utilizar la instrucción adduser --ingroup, sin olvidarnos de ejecutar la instrucción como super-usuario.

```console
sudo adduser gearoid --ingroup office1
sudo adduser paul --ingroup office1
```

-- Tendremos que asignarles unas contraseñas a cada usuario previamente creado.

## Ejercicio04
· *Create the users anna and emma. These users must belong only to the group office2.*

-- Procedemos de la misma manera que en el caso anterior.

```console
sudo adduser anna --ingroup office2
sudo adduser emma --ingroup office2
```

## Ejercicio05
· *As user gearoid, create a file named topsecret.txt in his home directory. Only this user must have access to this file, both for reading and writing.*

-- Para cambiarnos al usuario gearoid previamente creado, utilizamos la instrucción su, a continuación creamos el archivo topsecret.txt con el comando touch en su directorio home. Para terminar modificamos los permisos para que sólo él tenga acceso de lectura y escritura. Podemos hacer esto con el comando chmod y los valores de los permisos correspondientes, 4 si es lectura, 2 si es escritura y 1 si es ejecución.

```console
su gearoid
touch topsecret.txt
chmod 600 topsecret.txt
ls -l
```

-- Verificamos con el comando ls -l que se han modificado los permisos del archivo correctamente.

## Ejercicio06
· *Create another file named sales.txt, also as user gearoid,. All users in the same group as gearoid must have access to this file, both for reading and writing. The permissions for owner and the rest of users must remain as default. Check that you can modify the file if you access it as user paul.*

-- Volvemos a crear otro archivo llamado sales.txt desde el usuario gearoid con el comando touch, y modificamos sólo los permisos de grupo para lectura y escritura con el comando chmod, dejando los permisos del dueño y otros por defecto.

```console
su gearoid
touch sales.txt
chmod g+rw- sales.txt
exit
su paul
mcedit ../gearoid/sales.txt
```

-- Y probamos que se puede modificar cambiando el contenido del archivo con mcedit por ejemplo.
 
## Ejercicio07
· *As user anna, create a file named employees.txt. Any user must have access to read its content and any user in the same group must have access to read or write to it.*

-- Entramos como usuario anna con el comando su, y creamos el archivo employees.txt con el comando touch. Para cambiar los permisos utilizamos el comando chmod, dejando permisos de lectura para cualquier usuario y permisos de lectura y escritura para el grupo.

```console
su anna
touch employees.txt
chmod 464 employees.txt
```

## Ejercicio08
· *Create the user student (if it is not yet created). Copy the file employees.txt to the home directory of user student. Change the owner and the group of this file to student.*

-- Hemos de crear el usuario student si no esta aún creado, copiar el archivo employees.txt que creamos en el directorio anna al directorio student. Luego cambiaremos el dueño y el grupo de este archivo al usuario student.

```console
sudo mv /home/anna/report.txt /home/student/
sudo chown student report.txt
sudo chgrp student report.txt
```

## Ejercicio17
· *Supose a user has read access to a file, but this file is in a directory for which the user has no read access. Could this user read this file? Try it.*

-- Hemos de suponer que un usuario tenga permisos de lectura a un archivo, pero que ese archivo esté en un directorio para el cual el usuario no tiene permisos de lectura. Tenemos que probar si dicho usuario puede leer ese archivo.

```console
su user
mkdir DirectorioPrueba
cd DirectorioPrueba
touch ArchivoPrueba.txt
cd
chmod 333 DirectorioPrueba
gedit DirectorioPrueba/ArchivoPrueba.txt
```

-- Evidentemente nos da error, por lo tanto no es posible acceder a archivos aunque tengamos los permisos necesarios si no tenemos dichos permisos en el directorio que lo/s contiene.


