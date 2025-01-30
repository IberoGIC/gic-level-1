# Nivel 6->7

## Problema

El archivo que contiene la contraseña está contenido en alguna parte del servidor y tiene las siguientes caracteristicas:

* Es propiedad del usuario bandit7
* Es propiedad del grupo bandit6
* Tamaño de 33 bytes

## Teoría

En el sistema de archivos de linux, en realidad el directorio `~` no es el de mayor jerarquía, el que verdaderamente es el de mayor jerarquia es `/`.

## Solución

<details>

<summary>Ver solución</summary>

Con las caracteristicas del archivo que nos describen en el nivel podemos pensar en un comando como el siguiente:

```bash
find -size 33c -user bandit7 -user bandit6
```

En primera instancia este comando no imprime nada a la terminal, sin embargo, esto se debe a que solo estamos buscando dentro del directorio `/home`, entonces lo que debemos hacer para lograr una busqueda a profundidad es buscar en el directorio `/`, con el comando:

```bash
 find / -size 33c -user bandit7 -user bandit6
```

Lo que nos arroja un resultado en el que se marca que no tenemos los permisos necesarios para acceder a los directorios, algo como lo siguiente:

```bash
find: ‘/drifter/drifter14_src/axTLS’: Permission denied
find: ‘/root’: Permission denied
find: ‘/snap’: Permission denied
find: ‘/tmp’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1689721/task/1689721/fd/6’: No such file or directory
find: ‘/proc/1689721/task/1689721/fdinfo/6’: No such file or directory
find: ‘/proc/1689721/fd/5’: No such file or directory
find: ‘/proc/1689721/fdinfo/5’: No such file or directory
find: ‘/home/bandit31-git’: Permission denied
```

Podemos deducir que el comando encontró al archivo que estabamos buscando, ahora solo tenemos que filtrar los resultados de los directorios a los que no tenemos permisos, entonces la manera de no leerlos es con la expresión `2<dev/null` en donde el `2` representa el archivo **stderr** en donde se imprimen los errores,
`<` que redireciona **stderr** a `dev/null`, un archivo que descarta todas las entradas que le llegan, entonces, nuestro comando final es:

```bash
find / -size 33c -user bandit7 -group bandit6 2</dev/null
```

Lo que nos da el archivo `/var/lib/dpkg/info/bandit7.password`, por lo que solo lo tenemos que leer con el siguiente comando:

```bash
cat /var/lib/dpkg/info/bandit7.password
```

</details>