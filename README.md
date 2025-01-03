# enrollment-wa-bot

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
