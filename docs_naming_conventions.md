---
title: "HomeLabNet - Naming Conventions & Syntax Standards"
type: documentation
status: published
owner: Richie
created: 2026-08-11
last_updated: 2026-08-16
tags:
  - homelab
  - standards
  - naming
  - sre
---

# 📄 Naming Conventions — HomeLabNet

Este documento establece la especificación sintáctica formal para nombrar archivos dentro del repositorio, así como las convenciones de nombres para componentes físicos y lógicos de **HomeLabNet** (hosts, interfaces, VLANs y contenedores).

---

## 1. Sintaxis de Nombres de Archivo

Todos los archivos del proyecto deben apegarse estrictamente a la siguiente estructura léxica:

$$\text{<prefijo>}\_\text{<tema\_principal>}[\_\text{<detalle\_o\_fecha>}].\text{<extension>}$$

### Reglas de Formato:
* **Estilo tipográfico:** Todo en minúsculas estrictas utilizando guiones bajos (`snake_case`). Prohibido el uso de espacios, mayúsculas o caracteres especiales.
* **Sin separadores de ruta:** No incluir barras (`/` o `\`) en el nombre de los archivos dentro de la raíz del proyecto.
* **Formato de Fechas:** Cuando un archivo requiera fecha (auditorías, snapshots, revisiones), utilizar el estándar ISO 8601: `YYYY-MM-DD` o `YYYY-QQ` para trimestres.
* **Extensiones Estándar:** 
  * Documentación: `.md`
  * Datos crudos / Volcados técnicos: `.txt`, `.json`, `.yaml`
  * Recursos visuales: `.png`, `.svg`

### Ejemplos Válidos vs. Inválidos:
* ✅ `inventory_hardware.md`
* ✅ `reviews_security_2026-08.md`
* ✅ `diagrams_physical.png`
* ❌ `Inventory Hardware.md` *(Contiene mayúsculas y espacios)*
* ❌ `docs/blueprint.md` *(Utiliza carpetas anidadas no permitidas)*
* ❌ `notes.md` *(Nombre ambiguo sin prefijo de dominio)*

---

## 2. Convenciones para Infraestructura y Red

Para asegurar coherencia entre la documentación y la configuración técnica real, se aplican las siguientes reglas:

### A. Nombres de Hosts y Servidores
* Utilizar formato en minúsculas con guiones medios (`kebab-case`).
* Estructura: `<rol_o_modelo>-<descriptor>` (ej. `phoenix-core`, `router-tplink-ax11000`, `sw-oficina-01`).

### B. Segmentos y VLANs
* Los identificadores de VLAN en documentación y configuración siguen el patrón: `VLAN_<ID>_<NOMBRE_ZONA_UPPERCASE>`.
* Ejemplos: `VLAN_10_MGMT`, `VLAN_20_TRUSTED`, `VLAN_30_SERVERS`, `VLAN_40_IOT`.

### C. Servicios y Contenedores
* Nombres de contenedores y servicios en minúsculas descriptivas: `pihole-primary`, `traefik-proxy`, `home-assistant`.

---

## 📝 Control de Cambios y Autoría

* **Autor:** Richie
* **Fecha de última actualización:** 2026-08-16
* **Versión del documento:** 1.0.0
