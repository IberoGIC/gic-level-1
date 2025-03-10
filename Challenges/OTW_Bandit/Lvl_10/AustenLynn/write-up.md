# Nivel 9->10

## Problema

En este nivel se nos da un archivo que no solo tiene caracteres legibles, por lo que para encontrar la contraseña
necesitamos buscar el caracter `=`, porque la contraseña esta en una linea con estos carateres

## Teoría

El comando `strings` nos permite buscar caracters legibles en archivos.

## Solución

<details>

<summary>Ver solución</summary>

Para poder encontrar la candena con los carateres legibles usamos el comando `strings` y mediante el comando grep buscamos las lineas que contengan caracter `=` que contenga el caracter `=`, encadenamos el resultado de un comando con el otro usando `|`.

```bash
strings data.txt | grep = 
```

</details>
