# Nivel 0-1

## Teoría


## Problema

Ingresar al nivel 0  usando **ssh**

## Solución

<details>
<summary><u>Ver solución</u></summary>

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
