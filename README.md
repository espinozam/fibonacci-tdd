# [CI/CD] Pipeline con aplicación Java – Fase 2

En esta fase se propone construir un pipeline de CI/CD aplicado al proyecto Fibonacci TDD desarrollado en la fase anterior.

## GitHub Actions

GitHub Actions es una herramienta integrada en GitHub que permite automatizar procesos como la compilación del código y la ejecución de tests.
Estos procesos se definen mediante **workflows**, que se ejecutan automáticamente cuando se produce un evento como un push o un pull request.

## Actions utilizadas

Se han utilizado las siguientes Actions:

* **actions/checkout@v4**: action oficial que permite descargar el código del repositorio en el entorno de ejecución
* **actions/setup-java@v4**: action oficial que configura la versión de Java necesaria para el proyecto
* **Apache Maven**: herramienta utilizada para compilar el proyecto y ejecutar los tests mediante el comando mvn test

## Configuración del workflow

El workflow se define en el archivo:

```
.github/workflows/ci.yml
```

Este workflow se activa cuando se realiza un push o un pull request sobre la rama principal y ejecuta los siguientes pasos:

1. Descarga del repositorio
2. Configuración del entorno Java (Java 17)
3. Compilación del proyecto y ejecución de los tests

## Resultados

La pipeline implementada permite:

* Ejecutar los tests de forma automática
* Detectar errores de manera inmediata
* Asegurar la correcta integración del código en la rama principal

Si todos los tests se ejecutan correctamente, la pipeline finaliza con éxito.
Si alguno de los tests falla, la ejecución se detiene y se notifica el error.