# Troubleshooting (Resolución de problemas)
## Los servicios de KEA se ejecutan como kea-dhcp4.service, kea-dhcp6.service o kea-ctrl-agent.service
### Para ver todos los registros de un servicio específico:
    journalctl -u kea-dhcp4.service
### Para los últimos registros (desde que arrancó el servicio):
    journalctl -u kea-dhcp4.service –e
### Ver logs en tiempo real
    journalctl -u kea-dhcp4.service -f
## Ejecutando *journalctl -u kea-dhcp4.service* tendríamos un log como este:
    oct 03 10:42:11 servidor kea-dhcp4[1532]: INFO  [kea-dhcp4.dhcpsrv/1532] DHCPSRV_OPEN_SOCKET opened socket: 192.168.1.1:67
    oct 03 10:42:11 servidor kea-dhcp4[1532]: INFO  [kea-dhcp4.dhcpsrv/1532] DHCPSRV_CFGMGR_ADD_SUBNET added subnet 192.168.1.0/24
    oct 03 10:42:12 servidor kea-dhcp4[1532]: WARN  [kea-dhcp4.dhcpsrv/1532] DHCPSRV_CLASS_UNKNOWN client class 'iot-devices' not defined
    oct 03 10:42:13 servidor kea-dhcp4[1532]: ERROR [kea-dhcp4.alloc-engine/1532] ALLOC_ENGINE_V4_ALLOC_ERROR failed to allocate an IPv4 address: no free leases in pool 192.168.1.100-192.168.1.150
    oct 03 10:42:15 servidor kea-dhcp4[1532]: INFO  [kea-dhcp4.leases/1532] DHCP4_LEASE_GRANTED lease 192.168.1.101 for client hwaddr=08:00:27:1c:2a:3b
    oct 03 10:42:17 servidor kea-dhcp4[1532]: INFO  [kea-dhcp4.leases/1532] DHCP4_LEASE_RENEW lease 192.168.1.105 renewed for client hwaddr=08:00:27:aa:bb:cc
## Explicación de la estructura de un log
    oct 03 10:42:13 servidor kea-dhcp4[1532]: ERROR [kea-dhcp4.alloc-engine/1532] ALLOC_ENGINE_V4_ALLOC_ERROR failed to allocate an IPv4 address: no free leases in pool 192.168.1.100-192.168.1.150
### oct 03 10:42:13 
    Fecha y hora del evento (mes día hh:mm:ss).
### servidor
    El hostname de la máquina que genera el log.
### kea-dhcp4[1532]:
    kea-dhcp4 → Nombre del servicio que genera el log (puede ser kea-dhcp4, kea-dhcp6, kea-ctrl-agent, etc.).
    [1532] → PID (Process ID) del proceso en ejecución.
### ERROR 
    Nivel de severidad del mensaje. KEA usa normalmente:
    INFO → Información general (inicio, leases concedidas).
    WARN → Advertencias (config dudosa, clases faltantes).
    ERROR → Problemas serios (no asigna IPs, fallos de base de datos).
    DEBUG → Solo si lo activas, da trazas detalladas.
### [kea-dhcp4.alloc-engine/1532]
    kea-dhcp4.alloc-engine → módulo o componente de KEA que generó el mensaje (alloc-engine, leases, dhcpsrv, etc.).
    /1532 → Repite el PID para rastrear el proceso.
### ALLOC_ENGINE_V4_ALLOC_ERROR
    El código de evento interno de KEA. → Es un identificador único que te ayuda a reconocer el tipo exacto de error en la documentación.
### failed to allocate an IPv4 address: no free leases in pool 192.168.1.100-192.168.1.150
    El mensaje descriptivo en texto plano, con detalles concretos del fallo.
## Varios ejemplos de errores que pueden aparecer log
### Errores de configuración
Suceden cuando la configuración JSON no es válida o tiene parámetros mal definidos.
#### Ejemplo:
    ERROR [kea-dhcp4.dhcpsrv] DHCPSRV_CFGMGR_SUBNET invalid subnet definition: missing "pools" entry
    ERROR [kea-dhcp4] KEA_CONFIG_LOAD_FAIL failed to load configuration file /etc/kea/kea-dhcp4.conf: JSON parse error at line 12
### Errores de red / puertos
#### KEA necesita escuchar en puertos específicos (67/UDP para DHCPv4, 547/UDP para DHCPv6). Si ya están en uso o hay permisos insuficientes:
    ERROR [kea-dhcp4] DHCPSRV_OPEN_SOCKET_FAIL failed to open socket on interface eth0, port 67: address already in use
    ERROR [kea-dhcp6] DHCPSRV_SOCKET_BIND socket bind failed: Permission denied
## Hecho por:
`Pablo Sainz de la Maza Rodríguez`