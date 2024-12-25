# Nivel 0

## Problema

Ingresar al nivel 0  usando **ssh**

## Teoría

El objetivo de este nivel es familiarizarse con el comando **ssh** (Secure Shell). Este comando se utiliza para conectarse de manera remota a otra máquina y está diseñado para establecer una comunicación cifrada entre dos hosts en una red insegura.

## Solución

<details>
<summary>Ver solución</summary>

El comando ssh tiene la siguiente estructura:

```bash
ssh {usuario}@{servidor} -p {puerto} 
```

- **usuario**: El nombre del usuario al que deseas conectarte.
- **servidor**: Puede ser un nombre de dominio (como una URL) o una dirección IP.
- **puerto**: Es el número del puerto al que el servidor está escuchando conexiones SSH (por defecto, el puerto es 22).

Usando la información proporcionada en este nivel, el comando para conectarse sería:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

</details>
.