
# Configuración de Reservas (Asier Rodríguez)

## Resumen

Guía rápida para revisar las MAC en la red y configurar reservas (IP fijas por MAC) en el servidor DHCP editando el fichero principal de configuración.

## Requisitos

- Acceso con privilegios de administrador (sudo).
- Tener instalado `nmap` para detectar hosts y MACs en la red.

## 1) Ver las MAC en la red

Usa nmap en modo ping-scan para listar los equipos de una subred y ver sus MACs:

```bash
nmap -sn <red>/<máscara>
# ejemplo: nmap -sn 192.168.1.0/24
```

Si `nmap` no está instalado, en Debian/Ubuntu puedes instalarlo con:

```bash
sudo apt update; sudo apt install -y nmap
```

En otras distribuciones usa el gestor de paquetes correspondiente (yum, dnf, pacman, etc.).

## 2) Editar el fichero de configuración principal

Edita el fichero principal del servidor DHCP. Por ejemplo:

```bash
sudo nano /etc/dhcp/dhcpd.conf
```

Ve al final del archivo y añade la reserva con la siguiente sintaxis:

```conf
# Reserva para servidor web
host servidor-web {
    hardware ethernet 08:00:27:aa:bb:cc;
    fixed-address 192.168.1.10;
}
```

- `servidor-web`: nombre del host (puedes elegir cualquier identificador legible).
- `08:00:27:aa:bb:cc`: MAC del equipo (hardware ethernet).
- `192.168.1.10`: IP fija que se asignará siempre a esa MAC (fixed-address).

Se recomienda comentar cada reserva (con `#`) o añadir una línea comentada arriba para describir a qué equipo pertenece la reserva. Por ejemplo:

```conf
# Reserva para: PC-oficina-3 — Equipo: Asier (Notebook)
host pc-oficina-3 {
    hardware ethernet aa:bb:cc:dd:ee:ff;
    fixed-address 192.168.1.50;
}
```

## 3) Reiniciar el servicio DHCP

[Gestion de servicios](06-gestion-servicio.md)