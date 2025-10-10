# Backend de almacenamiento / BD leases

- **Kea** es un servidor **DHCP moderno y modular** que nos permite administrar los datos en diferentes bases de datos gracias a su **backend de almacenamiento flexible**, en dichas **bases de datos** almacenaremos los **leases**.

- Los **leases** (asignaciones de IP) deben almacenarse para persistencia y alta disponibilidad.

### Tipos de bases de datos permitidos:

#### memfile (por defecto)
- Archivo local (`/var/lib/kea/kea-leases4.csv`)
- Simple, pero no recomendado para producción

####  MySQL
- Base de datos relacional  
- Persistente y escalable  
- Ideal para entornos productivos

####  PostgreSQL
- Alternativa a MySQL con las mismas ventajas

####  Redis (opcional, como caché)
- Mejora el rendimiento en *setups* avanzados
