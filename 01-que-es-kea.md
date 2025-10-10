#  KEA DHCP — Servidor DHCP de ISC

##  ¿Qué es KEA?

**Kea** es un **servidor DHCP de código abierto** desarrollado por el **Internet Systems Consortium (ISC)**.  
Su función principal es asignar **direcciones IP y parámetros de red** a los clientes de forma automática, tal como lo hace cualquier servidor DHCP tradicional.

Kea fue diseñado para ser una **evolución moderna, modular y de alto rendimiento** respecto a su predecesor **ISC DHCP**.

###  Características principales

- Soporte para **DHCPv4** y **DHCPv6**  
- Administración mediante **API RESTful (control remoto)**  
- Almacenamiento en **MySQL, PostgreSQL o Cassandra**  
- **Alta disponibilidad (HA)** entre servidores  
- Extensible mediante **hooks** (módulos en C++ o Python)  
- **Rendimiento superior** y **configuración dinámica** sin reinicio

---

##  Origen y evolución

- **Inicio del desarrollo:** alrededor de **2011**  
- **Primera versión estable (1.0.0):** enero de **2016**  
- **Proyecto mantenido activamente** por ISC desde entonces  

Kea se creó para responder a las necesidades modernas de redes dinámicas, gran escala y automatización, que el antiguo **ISC DHCP (dhcpd)** ya no podía satisfacer eficientemente.

---

##  Sustitución

Kea fue desarrollado para **reemplazar al servidor**:

> **ISC DHCP** (también conocido como *dhcpd*)

El proyecto **ISC DHCP fue oficialmente descontinuado en 2022**, y el **ISC recomienda migrar a Kea** como su sucesor oficial.

---

## ⚙️ Versiones de KEA

| Versión | Año / Fecha | Características principales |
|----------|--------------|------------------------------|
| **1.0.0** | 2016 | Soporte básico de DHCPv4 y DHCPv6 |
| **1.1.x** | 2017 | Integración con bases de datos MySQL/PostgreSQL |
| **1.2 – 1.4** | 2017–2018 | Alta disponibilidad (HA), API REST, hooks |
| **1.6 – 1.8** | 2019–2020 | Mejoras en rendimiento y estabilidad |
| **1.9.x** (desarrollo) | 2020–2021 | Funciones experimentales y pre-2.0 |
| **2.x** | 2022–Actualidad | Migración a Python 3, seguridad, HA avanzada, automatización |

>  **La rama estable actual** es **2.x**, con actualizaciones periódicas de seguridad y mantenimiento.

---

##  Resumen general

| Aspecto | Detalle |
|----------|----------|
| **Nombre completo** | ISC Kea DHCP Server |
| **Desarrollador** | Internet Systems Consortium (ISC) |
| **Lenguaje principal** | C++ |
| **Reemplaza a** | ISC DHCP (dhcpd) |
| **Primera versión** | 2016 |
| **Última rama estable** | 2.x |
| **Licencia** | MPL 2.0 (Mozilla Public License) |

---

##  Conclusión

**Kea DHCP** representa la **nueva generación de servidores DHCP** desarrollada por ISC, enfocada en rendimiento, flexibilidad y automatización.  
Con soporte moderno para **API, bases de datos y alta disponibilidad**, Kea se ha convertido en el **reemplazo recomendado** para entornos que antes utilizaban **ISC DHCP**.



