# Nivel 12->13

## Problema

Se nos menciona que el archivo que `data.txt` contiene un hexdump de el archivo que contiene la
contraseña, tambien se nos menciona que este archivo fue comprimido varias veces. 
## Teoría

Un `hexdump` es una forma de mostar datos binarios en una forma más legible, usando numeros hexadecimales, la estructura basica es similar a la siguiente:

```bash
00000000  30 31 32 33 34 35 36 37  38 39 41 42 43 44 45 46  |0123456789ABCDEF|
```
Dentro de esta estructura podemos identificar 3 columnas la primera con el desplazamiento de los datos en el archivo, en palabras más simples, la posicion de los datos, en la segunda columna los bytes en hexadecimal y en la ultima columna lo caracteres en `ASCII`.

En Linux el comando xxd nos permite generar `hexdumps`, tambien no permite revertirlos con la bandera -r.



## Solución

<details>

<summary>Ver solución</summary>

Como primer paso podemos copiar `data.txt` a un directorio temporal que nos permita trabajar con el de forma libre

```bash
mkdir /tmp/AustenLynn
cp data.txt /tmp/AustenLynn
```

Con nuestro archivo en la caperta correspondiente podemos empezar a identificar el tipo de compresión que se utilizó, el formato de compresión utilizado lo podemos identificar observando el numero magico, que simplemente es un identificador que tiene cada archivo al inicio del mismo.


```bash
00000000: 1f8b 0808 83c9 8768 0203 6461 7461 322e  .......h..data2.
```

En la primera linea podemos identificar `1f 8b` que es el numero magico de archivos `.gz`. Con esto podemos revertir el `hexdump` con el formato adecuado.

```bash
xxd -r data.txt archivoRevertido.gz
```
Con el archivo ya en su formato apropiado podemos proceder a descomprimir con el siguiente comando:

```bash
gzip -d archivoRevertido.gz
```
Si intentamos leer el archivo depués de descomprimirlo por primera vez podemos observar que no todavia no podemos ver la contraseña, entonces hacemos otro `hexdump` para ver el numero magico una vez más:

```bash
xdd archivoRevertido
```
la primera linea del `hexdump` es la siguiente:

```bash
00000000: 425a 6839 3141 5926 5359 b33d 8af8 0000  BZh91AY&SY.=....
```
En este caso tomando encuenta los primeros 6 digitos podemos ver que es un archivo `bzip2`, con esto, renombramos de manera apropiada:

```bash
mv archivoRevertido archivoRevertido.bz2
```
Una vez más vemos el numero magico que ahora es de un archivo `gzip` nuevamente, repetimos los pasos anteriores para descomprimir. Con el archivo descomprimido podemos hacer el `hexdump` y vemos lo siguiente:

```bash
00000000: 6461 7461 352e 6269 6e00 0000 0000 0000  data5.bin.......
```
Podemos observar lo que parece un nombre de archivo, por lo que podemos asumir que es un archivo TAR, entonces lo descomprimimos una vez más:

```bash
tar -xf archivoRevertido.tar 
```
Lo que nos resulta en el archivo data5.bin, que cuando lo checamos nos muestra lo siguiente:

```bash
xxd data5.bin | head
00000000: 6461 7461 362e 6269 6e00 0000 0000 0000  data6.bin.......
```
podemos asumir un archivo TAR nuevamente y repetir los pasos, apartir de aqui los metodos se repiten hasta el final que nos da la contraseña, se considera trivial y un ejercicio para el lector:





</details>
