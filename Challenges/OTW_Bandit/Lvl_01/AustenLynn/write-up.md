# Nivel 0->1

## Problema

Leer la contraseña del siguiente nivel en el archivo **readme**

## Teoría

El objetivo de este nivel es familiarizarse con algunos comandos basicos del sistema de archivos de linux, algunos ejemplos son los siguientes:

`man` este comando nos permite ver el manual de otros comandos, dandonos una forma rapida de acceder a la documentación de un comando,
podriamos usar el comando  `man ssh` para mostrar la acceder a una descripcion y a las banderas de `ssh`.

`ls` Este comando lista los archivos del directorio actual. De forma predeterminada, muestra los nombres de los archivos, pero con diferentes opciones (`-l`, `-a`, entre otras) se puede obtener más información, como permisos, tamaños y fechas de modificación, o incluso listar archivos ocultos.

`cat` este comando nos permite concatenar  archivos a la  salida estandar, en ortras palabras puede leer archivos e imprimirlos a la terminal 

## Solución

<details>
<summary>Ver solución</summary>

Una vez logeados en el servidor de `bandit0` podemos usar el comando `ls` para verificar que el archivo **readme** exista. De forma que podamos ejecutar el siguiente comando:

```bash
cat readme
```

El comando concatena el archivo a la salida estandar y nos muestra un mensaje de bienvenida junto con la contraseña
</details>
