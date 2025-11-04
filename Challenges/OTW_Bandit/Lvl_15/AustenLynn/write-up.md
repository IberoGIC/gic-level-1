# Nivel 13 -> 14

## Problema

Se nos menciona que para obtener la contraseña debemos de enviar la contraseña del nivel actual, al puerto 30000

## Teoría

Los puertos son una parte fundamental, de la forma en la que esta estructurado el internet, los puertos son la forma que tiene un sistema operativo de identificar a que lugar o aplicación tiene que ir algun paquete que haya recibido.
El comando `nc` o netcat nos permite abrir un socket lo que le permite conectarse al otro socket (modo cliente) o esperar otras conexiones (modo servidor).

## Solución

<details>

<summary>Ver solución</summary>

Para enviar la contraseña del nivel actual al puerto 30000 usamos el siguiente comando:

```bash
echo "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS" | nc localhost 30000
```
Simplemente, hace la conexion al puerto 30000 y envia la contraseña del nivel actual

</details>
