# Nivel 5->6

## Problema

El archivo que contiene la contraseña está contenido en el fondo de un arbol de directorios y tiene las siguientes caracteristicas:

* texto plano
* tamaño de 1033 byte
* no ejecutable

## Teoría

El comando `find` es un comando que nos permite econtrar archvivos con ciertas banderas como:

* `type` permite filtrar basado  tipo del archivo que se va a listar como resultado del comando.
* `size` permite encontrar archivos basados en el tamaño del archivo.
* `executable` que busca los archivos ejecutables.
* `exec` que permite ejecutar otros comandos dentro del comando find.

estas banderas son cruciales para la busqueda de archivos dentro de servidores.

## Solución

<details>

<summary>Ver solución</summary>

Teniendo en cuenta que nos dan varios parametros para buscar el archivo, por lo que podemos aplicar uno por uno, para probar nuestra suerte, con un comando como el siguiente:

```bash
find -size 1033c # c se utiliza para indicar el tamaño en bytes.
```

Por suerte este comando el resultado del comando es el siguiente:

```bash
./inhere/maybehere07/.file2
```

En este caso convenientemente solo existe un archivo con tamaño de 1033 bytes, esto es coincidencia, algo que no siempre va a pasar, 
entonces, en realidad el comando completo que no nos fallaría en otro caso es más parecido a lo siguiente:

```bash
find -type f -size 1033c ! -executable -exec file '{}' \; | grep ASCII
```

Bastante complejo, expliquemoslo bandera por bandera:

* `type` filtra a todos los archivos que no son texto plano.
* `size` busca el  tamaño especificado. 
* `executable`  busca los archivos ejecutables, sin embargo, en este caso agregamos `!` para negar la bandera y solo buscar los no ejecutables.
* `exec` este comando ejecuta al comando file que nos regresa la naturaleza del archivo  `'{}'` simplemente sustituye el nombre del archivo, cabe agregar que -exec tiene que terminar con `;` y le agregamos `\` para escapar a `;` para que no ocurra *shell expansion*.
Esto nos lista todos los archivos del mismo tamaño, no ejecutables junto con la naturaleza del archivo.

```bash
./inhere/maybehere07/.file2: ASCII text, with very long lines (1000)
```

ahora solo faltaría filtrar por el tipo de archivo, tomando esto en cuenta tenemos que utilizar el operador `|` el cual nos permite pasar el resultado de cierto comando a otro comando en este caso `grep` un comando que nos permite buscar patrones en archivos, es por esto que buscamos la cadena `ASCII`.


</details>
