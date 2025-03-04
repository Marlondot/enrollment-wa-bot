# enrollment-telegram-bot

Como prueba de concepto se espera usar la interfaz sobre la API de telegram: [PTB](https://github.com/python-telegram-bot/python-telegram-bot), como conexión principal para llevar funcionalidades de contabilidad y registro de usuarios

## ¿Qué tipo de funcionalidades?

Como primera idea, podemos imaginar la funcionalidad de un contador, en la que el usuario al enviar un mensaje con un número entero se registra en una base de datos la fecha en la que ocurrió el guardado, y el número asociado. 

A pesar de que en un principio suene básico, esto podría funcionar como base para un sistema que guarde asistencias dados números de identificación.

## ¿Cómo hacerlo?

### PTB

Para comenzar se puede revisar el [quick start](https://github.com/python-telegram-bot/python-telegram-bot/wiki/Extensions---Your-first-Bot), a partir del cual se crea un bot con funcionalidad básica que se puede correr en local.

### Testing

Se puede pensar en incluir testing. Por una parte, los tests van a ser más fáciles de hacer mientras más [desacoplada](https://softwareengineering.stackexchange.com/a/244478) se encuentre toda la aplicación, es decir: no poner todo sobre una misma función, tratar de dividir por funcionalidades.

Para testing unitario se puede usar [pytest](https://docs.pytest.org/en/stable/getting-started.html#create-your-first-test)


### Base de datos

Para pruebas locales se puede crear una [conexión local MySQL](https://github.com/Lunes313/StreamlitProyect/blob/main/database.py)

Además para probar con una base de datos en nube se puede usar la [capa gratuita de MongoDB](https://www.mongodb.com/pricing) 

También se pueden buscar otras maneras de hosting para bases de datos en [foros](https://www.reddit.com/r/webdev/comments/vc2hpc/any_websites_where_i_can_host_sqlite_db_for_free/), la  idea es no cerrarse a explorar

## Tareas

- [ ] Crear funciones de queries para la base de datos, esto es importante para [abstraer la capa de persistencia y separarla de la capa de dominio](https://martinfowler.com/eaaCatalog/repository.html) Para esto usaremos MySQl en local, luego la idea será explorar el deploy en una VPS. En un principio hay mucha mano libre para esto, entonces no hay restricciones sobre cómo organizar las funciones. Mi recomendación es pensar en un repositorio como en funciones del lenguaje (python) que hacen CRUD sobre una tabla de SQL, por cada tabla en la base de datos existe un repositorio. (MID)

- [ ] Crea una función handler y la función main que pregunte y reciba un número enviado por mensaje, además de que llame a la función del repositorio, como son dos tareas diferentes se puede llamar a una función placeholder y luego corregirla por la función real cuando la del repositorio esté lista. (MID)

## PRs

Vamos a manejar un flujo sencillo de PRs, en el que cada nueva feature o cambio será hecho a partir de una rama sacada desde master (lo más común es que en el flujo existan la rama de develop y de master, pero para este caso vamos a obviarlo), y para hacer un merge a master vamos a hacer peer review a los cambios introducidos, proponer cambios o dar sugerencias. 


## Como correr VENV

A la hora de usar python entre proyectos lo ideal es usar un ambiente virtual o virtual environment

Para crear y activar el ambiente virtual se tienen que usar los siguientes comandos en la terminal:

```bash
python -m venv venv
venv\Scripts\activate
```

Luego dentro de la misma terminal se notará entre paréntesis un "venv" que es el nombre de nuestro ambiente.

A continuación usaremos el siguiente comando para instalar en el ambiente todas las dependencias necesarias para el proyecto:

```bash
pip install -r "requirements.txt"
```

Cada vez que se agregue o necesita una nueva dependencia esta se debe añadir al archivo de requerimientos de proyecto, que en este caso es "requirements.txt"

En caso de que haya una diferencia de dependencias no olvidar instalar nuevamente las dependencias con el comando (siempre que se actualice este archivo)