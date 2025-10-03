# **Instalacion de KEA**
> Para la instalación de **KEA** en **Debian 13** hay que introducir el siguiente comando en la terminal:
> apt -y install kea-dhcp4-server
> Al instalar **KEA** se creará el directorio:
> **/etc/kea/**
> Y dentro del directorio anterior los archivos:
>> **kea-dhcp4.conf**
>> Configuración del servidor **DHCP** para **IPv4** (más común).
>> **kea-dhcp6.conf**
>> ​Configuración para el servidor **DHCPv6** (si se usa).​
>> **kea-ctrl-agent.conf**
>> Configuración del agente de control (opcional, para API REST).
>> **kea-netconf.conf**
>> Configuración de red (si se utiliza iKea en modo gestionado por **Netconf**).​
>> **kea-logging.conf**
>> Configuración del sistema de logging (a veces integrado en los otros .conf).
