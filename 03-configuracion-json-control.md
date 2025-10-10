## Configuración JSON y control dinámico
### Antonio Díaz González


La configuración de **KEA** se realiza a través de ficheros en **formato JSON**, que son el estándar para el proyecto KEA. El fichero de configuración es **un único objeto JSON** que define cómo el servidor Kea DHCPv4 debe funcionar. Para gestionar estos ficheros, se puede usar herramientas como **JQ para validar** y dar formato automáticamente.

Para Instalar la herramienta de validación JQ podemos hacerlo mediante el comando:​ **sudo apt-get install jq**

Aun así, acompañándonos de esta breve guía que nos dirá como hacerlo y nos explica el funcionamiento del programa podremos entenderlo de una mejor forma: https://www.linode.com/docs/guides/using-jq-to-process-json-on-the-command-line/?lang=es​

JQ puede servir para realizar **varias cosas** como filtrar funciones,  transformar el JSON a otro formato o cambiar el formato del JSON para que queda más legible (pretty-print). Nosotros lo vamos a usar para **validar el archivo JSON**, que es lo que nos interesa.​

Para validar un archivo basta con introducir el comando **"jq empty archivo.json"**. Si el Archivo es válido, no muestra nada y el comando termina con éxito, si no lo es, muestra un error de sintaxis indicando dónde falla.​

​Aqui os dejo un ejemplo de cada caso:

Cuando el **archivo JSON** es **valido** :

![](KEA/img/Bien.png)

Cuando el **archivo JSON NO** es **valido** :

![](KEA/img/Mal.png)

