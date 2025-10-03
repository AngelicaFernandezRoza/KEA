# KEA: Servidor DHCP en Debian 13

El **KEA** es un servidor **DHCP** de **ISC** en **Debian 13** que permite definir exclusiones para que, dentro de un *pool* de direcciones dinámicas, no se asignen ciertas IP.  
Esto se configura en los archivos:

- `kea-dhcp4` (para IPv4)  
- `kea-dhcp6` (para IPv6)  

---

## Las Exclusiones

Las exclusiones permiten eliminar direcciones dentro de un rango dinámico para que no se asignen automáticamente a los clientes.

### Usos principales
- Reservar IP para **equipos con dirección fija** como *routers* o *servidores*.  
- Destinar direcciones para **futuras configuraciones**.  
- **Evitar conflictos en la red**.  

---

# Definición de Pools y Exclusiones en KEA

Un **pool** define el rango de direcciones disponibles para asignar dinámicamente a los clientes.  

### Ejemplo de definición de pool
```
"pools": [
  { "pool": "192.168.1.100 - 192.168.1.200" }
]
```
---

### Diferencia entre Exclusiones y Reservas

## 🔹 Exclusiones
- Impiden que ciertas IP se asignen automáticamente a los clientes.  
- Es decir, esas direcciones **quedan bloqueadas** y no pueden ser entregadas por el servidor DHCP.  

##  🔹 Reservas
- Asignan una **IP específica** a un cliente concreto.  
- Normalmente se identifican por la **dirección MAC** (en IPv4) o por el **DUID** (en IPv6).  
- Garantizan que ese dispositivo siempre obtenga la misma IP.





