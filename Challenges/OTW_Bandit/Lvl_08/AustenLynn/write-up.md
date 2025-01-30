# Nivel 7->8

## Problema

La contraseña se encuentra en un archivo con una lista de palabras que tienen posibles contraseñas a su lado, la contraseña se encuentra
al lado de la palabra **millionth**.

## Teoría

El comando `grep` nos permite  buscar expresiones dentro de archivos, con la siguiente estructura basica:

```bash
grep {patron} {archivo}
```

## Solución

<details>

<summary>Ver solución</summary>

Al momento de leer el archivo `data.txt` nos da un resultado parecido al siguiente:

```bash
offers  0DaHkFTzemUGDPhj2OCsynmx3vQhWVVD
reassigned      tOnH5UCzCIbKTlCfNwwDQXKryxmNNSqj
transmit        gaxkTk3FYQJnbX1ocKc3lVlrUlS6kYmR
maintenance's   ulYpgJXbLoAU6j5m00iAu81CWa8JI4Om
peppiest        040MKTlG4CL1qtYGcbKJv7S0pAyHfOIT
castigating     hRk2MJ6axSSRXiVqTGzKSe3TfQGj8TEM
polkas  wTvMPCLI37DA7GGEpU3Nx6JE3YFHytSZ
hotness djxxgKy29dUEeYYsyeOihHmOaA9g8Tef
```

Aqui podemos ver la estructura del archivo, por lo que ahora es claro que tenemos que encontrar **millionth**, lo podriamos hacer de manera manual, pero tardariamos mucho tiempo, por eso construimos el siguiente comando usando `grep`:

```bash
grep millionth data.txt
```

</details>
