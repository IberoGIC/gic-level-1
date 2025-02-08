# Nivel 8->9

## Problema

El nivel no presenta con un archivo lleno de posibles contraseñas, algunas se repiten,  y se nos menciona que la constraseña solo aparece una vez.

## Teoría

El comando `uniq` nos permite encontrar lineas repetidas, bajo la condición de que las lineas repetidas esten
adjacentes una a la otra.  

## Solución

<details>

<summary>Ver solución</summary>

Para encontrar la constraseña tenemos que usar el comando `uniq`, pero en el archivo las contraseñas identicas no se encuentran adjacentes una
a la otra, por lo que es necesario ordenar las contraseñas de forma que esten juntas y el comando `uniq` las pueda descartar. El ordenamiento
se puede lograr con el comando `sort`. Entonces nuestro comando queda asi:

```bash
sort data.txt | uniq -u
```

</details>
