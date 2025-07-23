# Nivel 11->12

## Problema

La contraseña ha almacenada en el archivo `data.txt` tiene lso caracteres rotados  13 posiciones lo que
significa que la `A` ahora es `N`, `B` se convierte en `O` y asi sucesivamente.

## Teoría

El comando `tr` nos permite "traducir" caracteres del `stdin`, por ejemplo:

```bash
tr A-Z a-z
```
el cual pasaria todos los caracteres de mayusculas a mininusculas.

## Solución

<details>

<summary>Ver solución</summary>

Para decodificar la constraseña imprimimos la contraseña y usamos con el comando `tr` de la siguiente forma:


```bash
 cat data.txt | tr ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz NOPQRSTUVWXYZABCDEFGHIJKLMnopqrstuvwxyzabcdefghijklm
```
`tr` recibe la cadena que va a remplazar con los caracteres por lo que los va a remplazar, en este caso la segunda cadena es el abecedario rotado 13 caracteres. 
</details>
