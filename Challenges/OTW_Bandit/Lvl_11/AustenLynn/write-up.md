# Nivel 10->11

## Problema

Se menciona que el archivo con la contraseña contiene datos codificados en base64.

## Teoría

La codificacion en base 64 convierte caracteres binarios en caracteres imprimibles, esto lo hace tomando 6 bits a la vez y mapeando ese valor a uno de los 64 caracteres del metodo de codificación. Por ejemplo:
`000000` se mapea a el caracter `A`.

El comando `base64` nos permite decodificar cadenas codificadas en base64

## Solución

<details>

<summary>Ver solución</summary>

Para encontrar la contraseña simplemente decodificamos el archivo `data.txt`, con la bandera `-d`

```bash
base64 -d data.txt
```

</details>
