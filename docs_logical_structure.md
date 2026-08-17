---
title: "HomeLabNet - Logical Structure & Domain Boundaries"
type: documentation
status: published
owner: Richie
created: 2026-08-11
last_updated: 2026-08-17
tags:
  - homelab
  - standards
  - architecture
  - sre
---

# 📄 Logical Structure — HomeLabNet

Este documento define las áreas conceptuales y el modelo de organización por dominios de **HomeLabNet**. Su objetivo es garantizar que la documentación y los recursos técnicos adjuntos sean modulares, trazables y 100% compatibles con Obsidian, GitHub y Cuadernos de Gemini mediante una topología plana basada en prefijos oficiales.

---

## 1. Principios de Organización

* **Estructura Plana Universal:** Todos los archivos residen en la raíz del repositorio o espacio de trabajo, evitando rutas relativas anidadas que rompan referencias entre plataformas.
* **Separación de Responsabilidades:** Cada documento y artefacto técnico pertenece a un dominio funcional identificado por su prefijo.
* **Agrupamiento Léxico:** El ordenamiento alfabético estándar agrupa automáticamente los archivos afines en cualquier explorador o visor de IA.

---

## 2. Dominios Funcionales del Repositorio

| Prefijo | Dominio Conceptual | Alcance y Tipo de Recursos |
| :--- | :--- | :--- |
| **`docs_`** | Arquitectura & Gobernanza | Blueprints de red, diseño de subredes/VLANs, topología y estándares. |
| **`inventory_`** | Inventario & Estado | Registro de activos físicos, interfaces de red, asignación de IPs/MACs. |
| **`sec_`** | Seguridad & Policiamiento | Matrices de firewall inter-VLAN, políticas Zero-Trust, VPNs y modelo de amenazas. |
| **`ops_`** | Operaciones & Resiliencia | Bitácora de cambios (Changelog), políticas de copia de seguridad 3-2-1 y runbooks de DR. |
| **`config_`** | Configuraciones de Red | Ajustes declarativos de switches, routers, reglas de firewall, certificados y DNS. |
| **`lab_`** | Laboratorio & Pruebas | Experimentos en hipervisores (Proxmox / Phoenix-Core), clústeres K3s y PoCs. |
| **`tasks_`** | Gestión & Roadmap | Backlog de ingeniería, tareas operativas pendientes e hitos de evolución. |
| **`diagrams_`** | Diagramas de Red | Diagramas lógicos, físicos y mapas vectoriales de segmentación. |
| **`reviews_`** | Auditoría & Reportes | Informes trimestrales de estado, reportes de desempeño y escaneos de seguridad. |
| **`archive_`** | Histórico & Deprecados | Documentación y esquemas históricos conservados para trazabilidad. |
| **`specs_`** | Manuales & Especificaciones | Hojas técnicas oficiales (*datasheets*) y manuales PDF de hardware y placas. |
| **`media_`** | Capturas & Evidencias | Screenshots de interfaces web, dashboards de observabilidad (Grafana) y evidencias. |
| **`dumps_`** | Volcados Técnicos | Salidas crudas de comandos de diagnóstico (`lshw`, `lspci`, `hwinfo`, `nmap`). |
| **`code_`** | Automatización & Scripts | Scripts de aprovisionamiento y mantenimiento (`.ps1`, `.sh`, `.py`). |
| **`compose_`** | Stacks de Contenedores | Definiciones declarativas de despliegue (`docker-compose.yaml`, manifests K3s). |
| **`backup_`** | Respaldos de Configuración | Exportaciones de configuración cruda de equipos de red y servicios (`.bin`, `.cfg`, `.conf`). |
| **`data_`** | Datos Estructurados | Tablas de datos crudos, mapeos de puertos y reservas DHCP (`.csv`, `.json`). |
| **`templates_`** | Plantillas de Documentación | Esqueletos preconfigurados de notas Markdown para estandarizar el vault. |

> Para consultar la sintaxis formal de nombres y extensiones permitidas, revisa [docs_naming_conventions.md](docs_naming_conventions.md).

---

## 3. Topología de Archivos del Repositorio

```text
homelabnet/
├── README.md
├── docs_logical_structure.md
├── docs_naming_conventions.md
├── docs_blueprint.md
├── docs_vlans_design.md
├── inventory_hardware.md
├── inventory_logical.md
├── sec_access_policies.md
├── sec_firewall_matrix.md
├── sec_threat_model.md
├── ops_changelog.md
├── ops_backup_and_retention.md
├── ops_runbooks_disaster_recovery.md
├── config_router_tp-link.md
├── config_dns_and_certificates.md
├── config_vlans.md
├── config_firewall_rules.md
├── lab_proxmox_experiments.md
├── lab_k3s_cluster_notes.md
├── tasks_backlog.md
├── tasks_roadmap.md
├── diagrams_physical.png
├── diagrams_logical.png
├── diagrams_vlans.png
├── specs_dp67bg_board_manual.pdf
├── media_grafana_dashboard.png
├── dumps_dp67bg_lshw_output.txt
├── code_proxmox_lxc_bootstrap.sh
├── compose_home_assistant_stack.yaml
├── backup_tplink_ax11000_20260816.bin
├── data_dhcp_reservations_export.csv
├── templates_hardware_device.md
├── reviews_quarterly_2026-Q3.md
├── reviews_security_2026-08.md
├── archive_old_wifi_topology_2024.md
└── archive_previous_blueprint.md
```

---

## 📝 Control de Cambios y Autoría

* **Autor:** Richie
* **Fecha de última actualización:** 2026-08-17
* **Versión del documento:** 1.1.0
