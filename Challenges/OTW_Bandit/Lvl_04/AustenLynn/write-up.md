# Nivel 3->4

## Problema

El archivo que contiene  la contraseña esta oculto dentro de un directorio .

## Teoría

En linux existen archivos que **ocultos** que generalmente son archivos de configuración del sistema  y no se listan de manera regular para evitar confusiones,
estos archivos comienzan con un punto `.` .

## Solución

<details>

<summary>Ver solución</summary>

Para encontrar el archivo oculto tenenmos que listar todos los archivos del directorio `inhere`, usando la bandera `-a` que lista todos los archivos de la ruta indicada, quedando
un comando como el siguiente:

```bash
ls -a inhere
```

El comando nos muestra el archivo `..Hiding-From-You`, entonces lo podemos leer con el siguiente comando:

```bash
cat  inhere/..Hiding-From-You

```

</details>
