# Nivel 1->2

## Problema

Leer el archivo nombrado **'-'**

## Teoría

'-' es un caracter especial en Linux , por lo que no es común encontrar archivos nombrados con este tipo de caracteres, debido a que generan un conflicto al momento de intentar modificar estos archivos,
en este tipo de casos se tiene que ser más especifico al momento de referenciar estos archivos.

## Solución

<details>
<summary>Ver solución</summary>

La manera de evitar la ambiguedad que se genera al intentar leer el archivo de forma convencional es usar `./` antes del nombre del archivo, para espeficar que nos referimos al directorio actual.
Lo que nos resulta en el siguiente comando:

```bash
cat ./-
```

</details>
