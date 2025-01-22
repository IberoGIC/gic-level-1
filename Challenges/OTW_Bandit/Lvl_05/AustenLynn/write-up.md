# Nivel 4->5

## Problema

El archivo que contiene  la contraseña es el unico con texto plano.

## Teoría

Dentro de Linux no  todos los archivo son de texto plano, también existen archivos que no son texto plano y no se pueden leer
por un humano, por lo que, existe el comando `file` que nos permite identificar el tipo de archivo con el que tratamos.

## Solución

<details>

<summary>Ver solución</summary>

Para identificar el archivo con el texto pñano dentro del directorio `inhere` solo tenemos que ultizar el comando `file` en todo el
directorio esto se puede lograr con el operador `*`  es el operador **wildcard** que se ultiliza para representar **cero o más caracteres**. Lo que nos deja con el siguiente comando para encontrar el archivo con el texto plano:

```bash
file inhere/*
```

El nos muestra el siguiente resultado:

```bash
inhere/-file00: data
inhere/-file01: data
inhere/-file02: data
inhere/-file03: data
inhere/-file04: data
inhere/-file05: data
inhere/-file06: data
inhere/-file07: ASCII text
inhere/-file08: data
inhere/-file09: data
```

Podemos ver claramente que el archivo con la contraseña es el archivo `-file07` el que podemos leer facilmente con el comando:

```bash
cat  inhere/-file07
```

</details>
