# Configuración del Servidor DHCP

El fichero de configuración está escrito principalmente en **JSON**.

## Sintaxis básica

- Las `#` se utilizan para escribir **comentarios**.
- Los `[` indican una **lista de valores**.
- Los `{` se utilizan para definir **objetos**.

## Estructura del fichero

El fichero está compuesto por un contenedor principal llamado `Dhcp4`.

Dentro de este contenedor se pueden definir:

- Las **interfaces de red**
- El **lease** (tiempo de arrendamiento de direcciones IP)
- Las **subredes IPv4** que el servidor gestionará
