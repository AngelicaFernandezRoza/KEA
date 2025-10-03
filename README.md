# Manual colaborativo de KEA en Debian 13

Este repositorio contiene apuntes elaborados por los estudiantes sobre la instalación y configuración del servidor **KEA DHCP** en **Debian 13**.

## 📚 Índice de contenidos

1. [¿Qué es KEA?](01-que-es-kea.md)
2. [Arquitectura modular](02-arquitectura-modular.md)
3. [Configuración JSON + control dinámico](03-configuracion-json-control.md)
4. [Backends de almacenamiento / BD de leases](04-backends-lease-db.md)
5. [Instalación de KEA en Debian 13](05-instalacion-debian13.md)
6. [Gestión del servicio](06-gestion-servicio.md)
7. [Fichero de configuración](07-fichero-configuracion.md)
8. [Configuración básica del servidor](08-configuracion-basica.md)
9. [Configuración de reservas](09-reservas.md)
10. [Configuración de exclusiones](10-exclusiones.md)
11. [Configuración de opciones adicionales](11-opciones-adicionales.md)
12. [Ejemplo de fichero de configuración](12-ejemplo-configuracion.md)
13. [Troubleshooting (resolución de problemas)](13-troubleshooting.md)

---

## 🔧 Cómo colaborar

1. Cada alumno tiene asignado un apartado.  
2. Edita directamente el archivo correspondiente (`xx-nombre-apartado.md`).  
3. Usa **Markdown** para formatear: títulos, listas, código, enlaces.  
4. Guarda y haz *commit* con un mensaje claro (ej. `Añadido apartado 05 - instalación`).  

👉 Si quieres, valida tu JSON con:  
```bash
jq . archivo.json
