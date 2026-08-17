---
title: "HomeLabNet - Central Index"
type: index
status: published
owner: Richie
created: 2026-08-11
last_updated: 2026-08-16
tags:
  - homelab
  - index
  - architecture
  - sre
---

# 🌐 homelabnet-infrastructure-evolution — Central Index

Bienvenido al índice central de **HomeLabNet**. Este repositorio y vault de Obsidian actúa como la fuente única de verdad (*Single Source of Truth*) para la arquitectura, inventario, segmentación y evolución continua de la red local e infraestructura.

> ℹ️ **Estándares del Repositorio:**
> * Para comprender las categorías funcionales y la organización lógica, consulta [docs_logical_structure.md](docs_logical_structure.md).
> * Para consultar la sintaxis de nombres de archivos, hosts y variables, revisa [docs_naming_conventions.md](docs_naming_conventions.md).

---

## 🧭 Módulos de Documentación

### 1. 📐 Arquitectura & Gobernanza (`docs_`)
* [docs_logical_structure.md](docs_logical_structure.md) — Estructura lógica oficial y áreas de dominio.
* [docs_naming_conventions.md](docs_naming_conventions.md) — Estándares y sintaxis de nombres.
* [docs_blueprint.md](docs_blueprint.md) — Blueprint global de arquitectura y topología de red.
* [docs_vlans_design.md](docs_vlans_design.md) — Definición de subredes, CIDR y propósitos de segmentación.

### 2. 🗄️ Inventario & Infraestructura (`inventory_`)
* [inventory_hardware.md](inventory_hardware.md) — Inventario físico consolidado de equipos, redes, consolas y domótica.
* [inventory_logical.md](inventory_logical.md) — Mapeo de direcciones IP, MACs, VLAN tags y servicios activos.

### 3. 🛡️ Seguridad & Policiamiento (`sec_`)
* [sec_access_policies.md](sec_access_policies.md) — Modelos Zero-Trust, VPN/Tailscale y VLANs aisladas.
* [sec_firewall_matrix.md](sec_firewall_matrix.md) — Matriz de tráfico inter-VLAN (Default-Deny).
* [sec_threat_model.md](sec_threat_model.md) — Modelo de amenazas y superficie de ataque.

### 4. ⚙️ Operaciones & Resiliencia (`ops_`)
* [ops_changelog.md](ops_changelog.md) — Historial de auditoría y modificaciones de infraestructura.
* [ops_backup_and_retention.md](ops_backup_and_retention.md) — Políticas 3-2-1, retención y pruebas de restauración.
* [ops_runbooks_disaster_recovery.md](ops_runbooks_disaster_recovery.md) — Procedimientos operativos ante fallos de energía o hardware.

### 5. 🛠️ Configuraciones & Servicios (`config_`)
* [config_router_tp-link.md](config_router_tp-link.md) — Parámetros WAN/LAN, DHCP y reservas del router principal.
* [config_dns_and_certificates.md](config_dns_and_certificates.md) — Registros DNS internos y Reverse Proxy (HTTPS).
* [config_vlans.md](config_vlans.md) — VIDs, puertos tagged/untagged en switches.
* [config_firewall_rules.md](config_firewall_rules.md) — Reglas activas y filtrado en frontera/LAN.

### 6. 🧪 Laboratorio & Pruebas (`lab_`)
* [lab_proxmox_experiments.md](lab_proxmox_experiments.md) — Pruebas en el servidor DP67BG (Phoenix-Core) y Proxmox VE.
* [lab_k3s_cluster_notes.md](lab_k3s_cluster_notes.md) — Despliegue de servicios y orquestación con K3s.

### 7. 📋 Planificación & Gestión (`tasks_`)
* [tasks_backlog.md](tasks_backlog.md) — Mejoras y tareas pendientes en la infraestructura.
* [tasks_roadmap.md](tasks_roadmap.md) — Hitos de evolución continua de HomeLabNet.

### 8. 📊 Diagramas & Mapas (`diagrams_`)
* [diagrams_physical.png](diagrams_physical.png) — Diagrama de topología y conexiones físicas.
* [diagrams_logical.png](diagrams_logical.png) — Diagrama de arquitectura lógica y flujo de datos.
* [diagrams_vlans.png](diagrams_vlans.png) — Esquema visual de segmentación y distribución de VLANs.

### 9. 🔍 Revisiones & Auditorías (`reviews_`)
* [reviews_quarterly_2026-Q3.md](reviews_quarterly_2026-Q3.md) — Reporte y revisión trimestral de infraestructura Q3 2026.
* [reviews_security_2026-08.md](reviews_security_2026-08.md) — Auditoría de seguridad, puertos expuestos y aislamiento de red.

### 10. 📦 Archivo Histórico (`archive_`)
* [archive_old_wifi_topology_2024.md](archive_old_wifi_topology_2024.md) — Esquema histórico de topología WiFi (descontinuado).
* [archive_previous_blueprint.md](archive_previous_blueprint.md) — Versión previa del blueprint de infraestructura.

---

## 📌 Convenciones del Vault
* **Enlaces e Imágenes:** Utilizar estrictamente enlaces relativos estándar CommonMark `[texto](archivo.md)` e imágenes `![alt](ruta/imagen.png)` sin sintaxis WikiLink.
* **Ubicación de Adjuntos:** Los recursos multimedia, diagramas y capturas se ubican en `./attachments/` o bajo el prefijo `diagrams_`.
* **Cero Secretos:** No almacenar contraseñas ni tokens en texto plano; documentar únicamente identificadores del gestor de credenciales.
* **Control de Cambios:** Todo ajuste de infraestructura debe registrarse en `ops_changelog.md` antes de realizar `git push`.

---

## 📝 Control de Cambios y Autoría

* **Autor:** Richie
* **Fecha de última actualización:** 2026-08-16
* **Versión del documento:** 1.0.0
