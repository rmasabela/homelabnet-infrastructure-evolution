---
title: "HomeLabNet - Naming Conventions & Syntax Standards"
type: documentation
status: published
owner: Richie
created: 2026-08-11
last_updated: 2026-08-17
tags:
  - homelab
  - standards
  - naming
  - sre
---

# 📄 Naming Conventions — HomeLabNet

Este documento establece la especificación sintáctica formal para nombrar archivos, adjuntos técnicos y componentes físicos/lógicos dentro de **HomeLabNet** (hosts, interfaces, VLANs y contenedores).

---

## 1. Sintaxis de Nombres de Archivo y Recursos

Todos los archivos del proyecto deben apegarse estrictamente al siguiente patrón léxico:

$$\text{<prefijo>}\_\text{<tema\_principal>}[\_\text{<detalle\_o\_fecha>}].\text{<extension>}$$

### Reglas de Formato:
* **Estilo tipográfico:** Todo en minúsculas estrictas utilizando guiones bajos (`snake_case`). Prohibido el uso de espacios, mayúsculas o caracteres especiales en nombres de archivo.
* **Sin separadores de ruta:** No incluir barras (`/` o `\`) en los nombres de archivo.
* **Formato de Fechas:** Cuando un recurso incluya fecha (snapshots, backups, auditorías), utilizar el estándar ISO 8601: `YYYYMMDD` (para backups/dumps compactos) o `YYYY-MM-DD` / `YYYY-QQ` (para revisiones y reportes).

---

## 2. Catálogo de Extensiones por Prefijo

| Prefijo | Tipo de Recurso | Extensiones Permitidas | Ejemplos Válidos |
| :--- | :--- | :--- | :--- |
| **`docs_`**, **`sec_`**, **`ops_`**, **`config_`**, **`lab_`**, **`tasks_`**, **`reviews_`**, **`archive_`**, **`templates_`** | Documentación y Plantillas | `.md` | `docs_blueprint.md`, `sec_threat_model.md`, `templates_hardware_device.md` |
| **`inventory_`** | Inventarios y Volcados | `.md`, `.txt`, `.json` | `inventory_hardware.md`, `inventory_homelab_snapshot_2026-08-01.txt` |
| **`diagrams_`**, **`media_`** | Recursos Gráficos | `.png`, `.jpg`, `.svg`, `.webp` | `diagrams_vlans.png`, `media_grafana_dashboard.png` |
| **`specs_`** | Documentos / Manuales | `.pdf` | `specs_dp67bg_board_manual.pdf` |
| **`dumps_`** | Diagnósticos y Logs | `.txt`, `.log`, `.json` | `dumps_dp67bg_lshw_output.txt` |
| **`code_`** | Scripts de Infraestructura | `.ps1`, `.sh`, `.py` | `code_proxmox_lxc_bootstrap.sh` |
| **`compose_`** | Despliegue de Servicios | `.yaml`, `.yml` | `compose_home_assistant_stack.yaml` |
| **`backup_`** | Backups Crudos | `.bin`, `.cfg`, `.conf`, `.xml`, `.tar.gz` | `backup_tplink_ax11000_20260816.bin` |
| **`data_`** | Datos Estructurados | `.csv`, `.json` | `data_dhcp_reservations_export.csv` |

---

## 3. Convenciones para Infraestructura y Red

### A. Nombres de Hosts y Servidores
* Formato en minúsculas con guiones medios (`kebab-case`).
* Estructura: `<rol_o_modelo>-<descriptor>` (ej. `phoenix-core`, `router-tplink-ax11000`, `sw-oficina-01`).

### B. Segmentos y VLANs
* Los identificadores de VLAN en documentación y configuración siguen el patrón: `VLAN_<ID>_<NOMBRE_ZONA_UPPERCASE>`.
* Ejemplos: `VLAN_10_MGMT`, `VLAN_20_TRUSTED`, `VLAN_30_SERVERS`, `VLAN_40_IOT`, `VLAN_50_CCTV`.

### C. Servicios y Stacks de Contenedores
* Formato en minúsculas descriptivas con guiones medios: `pihole-primary`, `traefik-proxy`, `home-assistant`.

---

## 📝 Control de Cambios y Autoría

* **Autor:** Richie
* **Fecha de última actualización:** 2026-08-17
* **Versión del documento:** 1.1.0
