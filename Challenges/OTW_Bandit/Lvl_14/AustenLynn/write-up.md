# Nivel 13 -> 14

## Problema

Se nos menciona que en este nivel, la contraseña se encuentra en el directorio ´/etc/
bandit_pass/bandit14´ y solo puede ser accedido desde e siguiente nivel, por lo que nos
proporcionan con una ´SSH key´.

## Teoría

Las llaves SSH son generadas con el uso de criptografia asimetrica, y son archivos codificados en base64 que almacena tus datos de manera estructurada. De forma que existe:

* Archivo de llave privada
* Archivo de de llave publica

El proceso de autenticación, funciona de forma que el cliente y el servidor establecen un canal seguro, en el que el servidor checa el usuario y detecta la llave publica, lo que lanza un reto al cliente que solo se puede resolver con la llave privada, cuando se verifica la firma, la autenticación procede.


## Solución

<details>

<summary>Ver solución</summary>

Para poder acceder al nivel 14, tenemos que descargar la llave privada a nuestro ambiente local, por lo que usamos scp para descargarla, con el siguiente comando:

```bash
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
```
Una vez la tenemos en nuestro ambiente local, podemos usar `ssh` para acceder al nivel con el siguiente comando:

```bash
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

</details>
