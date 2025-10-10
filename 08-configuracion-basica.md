# Configuración básica del servidor  
## Jaime Portilla

- **Archivo principal:** `/etc/kea/kea-dhcp4.conf`
- **Bloques principales:**
  - `interfaces-config` – Interfaz de red donde escucha Kea.
  - `lease-database` – Donde se guardan los arrendamientos.
  - `subnet4` – Configuración de subred y rango de IPs.
  - `option-data` – Parámetros adicionales como gateway y DNS.
  - `loggers` – Registro de actividad.
# Comandos Útiles Para La Configuración


- **Verificar archivo de configuración:**  
  `kea-dhcp4 -t /etc/kea/kea-dhcp4.conf`

- **La opción -t significa "test mode".**

- Si todo está correcto, mostrará:  
  `Configuration appears to be clean`

- Si hay errores (comas mal puestas, campos faltantes, errores de sintaxis JSON), los mostrará detalladamente.

### ¿Qué contiene?

- **Interfaces de red en las que escuchará solicitudes DHCP**
- **Subredes disponibles y rangos de IPs a asignar**
- **Opciones como gateway, DNS, tiempo de vida de los leases**

# Ejemplo de Configuración Básica en json
```json
{
  "interfaces-config": {
    "interfaces": [ "eth0" ]
  },
  "subnet4": [
    {
      "subnet": "192.168.1.0/24",
      "pools": [
        { "pool": "192.168.1.100 - 192.168.1.200" }
      ],
      "option-data": [
        { "name": "routers", "data": "192.168.1.1" },
        { "name": "domain-name-servers", "data": "8.8.8.8, 8.8.4.4" }
      ]
    }
  ]
}

