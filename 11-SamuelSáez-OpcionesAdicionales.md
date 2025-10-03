# Configuración de opciones adicionales Samuel Sáez​
### Para la configuración de las opciones adicionales hay que añadir, tras definir la red y su rango, "Option-Data" donde podremos definir las variables.​

Puerta de enlace (routers)​

Servidor DNS (domain-name-servers)​

Nombre del dominio (domain-name)​

Nombre del servidor TFTP (tftp-server-name)​

Dirección del servidor TFTP (tftp-server-address)​

### Para poder definir las opciones tenemos que escribir: {"name" (nombre de variable), "data": (datos de la variable)}

## CÓDIGO DE EJEMPLO​
    "option-data": [​

          { "name": "routers", "data": "192.168.1.1" },​

          { "name": "domain-name-servers", "data": "8.8.8.8, 8.8.4.4" },​

          { "name": "domain-name", "data": "midominio.local" },​

          { "name": "tftp-server-name", "data": "tftp.mired.local" },​

          { "name": "tftp-server-address",  "data": "192.168.1.250"  }​

        ]


