# Capitulo 12- Ejemplo de configuración de un servidor DHCP KEA
## Introducción
En este apartado se vera como se configura un servidor KEA con un ejemplo.
## Desarrollo del contenido técnico
La configuración de Kea se basa en un único archivo en formato JSON, normalmente ubicado en /etc/kea/kea-dhcp4.conf.     

Los elementos principales de una configuración básica son:

- **interfaces-config**: Define en qué interfaz de red escucha el servidor DHCP.  
- **lease-database**: Determina dónde se almacenan los leases de IP asignadas.  
- **subnet4**:Lista de subredes y pools de direcciones disponibles para clientes.  
- **option-data**: Incluye opciones como la puerta de enlace, servidores DNS y nombre de dominio.  
- **reservations**(opcional): Para asignar IP fijas a equipos específicos usando la MAC.  
- **control-socket**: Permite interactuar con el servidor en tiempo real usando kea-shell o API.  
- **loggers**: Configuración de registros y niveles de log.

## Ejemplo
En este caso en particular la interfaz es la et0, la red es la 192.168.10.0./24, el rango va desde 192.168.10.100 hasta 192.168.10.200, la ip del router o puerta de enlace es 192.168.10.1, el dns tiene las ip 8.8.8.8, 8.8.4.4, el nombre de dominio es red.local, se reserva a la mac 00:11:22:33:44:55 la ip 192.168.10.50, la duracion de la concesión es de 3600 segundos o 1 hora , el tiempo para renovar la ip es de  900 segundos o 15 minutos, si no se puede renovar la primera vez lo volvera ha intentar a los 1800 segundos o 30 minutos. 
````json
{
  "Dhcp4": {
    "interfaces-config": {
      "interfaces": [ "eth0" ]
    },

    "lease-database": {
      "type": "memfile",
      "persist": true,
      "name": "/var/lib/kea/dhcp4.leases"
    },

    "subnet4": [
      {
        "subnet": "192.168.10.0/24",
        "pools": [
          { "pool": "192.168.10.100 - 192.168.10.200" }
        ],
        "option-data": [
          {
            "name": "routers",
            "data": "192.168.10.1"
          },
          {
            "name": "domain-name-servers",
            "data": "8.8.8.8, 8.8.4.4"
          },
          {
            "name": "domain-name",
            "data": "red.local"
          }
        ],
        "reservations": [
          {
            "hw-address": "00:11:22:33:44:55",
            "ip-address": "192.168.10.50",
            "hostname": "equipo-fijo"
          }
        ]
      }
    ],

    "valid-lifetime": 3600,
    "renew-timer": 900,
    "rebind-timer": 1800,

    "control-socket": {
      "socket-type": "unix",
      "socket-name": "/run/kea/kea4-ctrl-socket"
    },

    "loggers": [
      {
        "name": "kea-dhcp4",
        "output_options": [
          {
            "output": "/var/log/kea-dhcp4.log"
          }
        ],
        "severity": "INFO",
        "debuglevel": 0
      }
    ]
  }
}
````
## Referencias
Para el desarrollo del contenido tecnico he utilizado la inteligencia artificial del buscador de google y para crear el ejemplo de configuracion he usado chatgpt donde he puesto hazme un ejemplo de configuracion de un servidor DHCP KEA.