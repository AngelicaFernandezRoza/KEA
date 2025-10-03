# Kea: DHCP modular, escalable y de alta disponibilidad

**Kea** es un servidor DHCP moderno desarrollado por ISC que supera las limitaciones de los servidores DHCP tradicionales gracias a su arquitectura **modular, flexible y altamente escalable**.

## 1. Arquitectura modular
Kea está construido como un conjunto de **procesos independientes**, cada uno especializado en una función concreta:

- **kea-dhcp4** → servidor DHCP para IPv4.  
- **kea-dhcp6** → servidor DHCP para IPv6.  
- **kea-dhcp-dns** → gestiona actualizaciones dinámicas de DNS.

Esta separación permite desplegar únicamente los módulos necesarios, optimizar recursos y facilitar la administración en entornos complejos.

## 2. Backends flexibles de almacenamiento
Kea separa la gestión de datos de la lógica del servidor mediante **backends de almacenamiento**, lo que aporta mayor flexibilidad, redundancia y escalabilidad:

- **Memfile** → archivos locales, ideal para despliegues pequeños o pruebas.  
- **Bases de datos SQL** → MySQL o PostgreSQL, para entornos con grandes volúmenes de clientes y necesidades de alta disponibilidad.

## 3. Extensibilidad mediante hooks
Una de las fortalezas de Kea es su sistema de **hooks**, módulos dinámicos que permiten **extender o complementar el comportamiento del servidor sin modificar el núcleo**. Esto permite añadir funcionalidades personalizadas de manera segura y flexible.

## 4. Gestión dinámica vía APIs
Kea utiliza **configuración en JSON** que puede modificarse en caliente, es decir, **sin reiniciar los servicios**, mediante:

- **REST API** → comandos para administrar el servidor desde aplicaciones externas.  
- **Agentes de gestión** → herramientas que interactúan con los servicios de Kea de manera remota o automatizada.

Esto facilita la operación en entornos grandes, automatizados o integrados con sistemas de orquestación.

## 5. Alta disponibilidad y escalabilidad
Kea soporta mecanismos de **failover**, asegurando que si un servidor principal falla, otro secundario toma el control automáticamente, evitando interrupciones del servicio. Su arquitectura modular y sus backends de base de datos permiten también un **escalado eficiente**, adaptándose a entornos desde medianas empresas hasta proveedores de servicios masivos.

---

## ✅ Resumen
Kea redefine los servicios DHCP tradicionales ofreciendo:

- Modularidad y procesos especializados.  
- Flexibilidad mediante hooks y backends configurables.  
- Gestión dinámica sin reinicios mediante REST API.  
- Alta disponibilidad y escalabilidad con failover y soporte para bases de datos.

Es, en definitiva, una solución moderna y robusta para cualquier infraestructura de red que busque **flexibilidad, control y continuidad de servicio**.
