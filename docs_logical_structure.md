---
title: "HomeLabNet - Logical Structure & Domain Boundaries"
type: documentation
status: published
owner: Richie
created: 2026-08-11
last_updated: 2026-08-16
tags:
  - homelab
  - standards
  - architecture
  - sre
---

# 📄 Logical Structure — HomeLabNet

Este documento define las áreas conceptuales y el modelo de organización por dominios de **HomeLabNet**. Su objetivo es garantizar que la documentación sea modular, trazable y compatible tanto con editores locales (Obsidian, VS Code) como con plataformas de IA (Gemini Notebooks, Copilot Projects).

---

## 1. Principios de Organización

Para mantener alta portabilidad y evitar árboles de directorios profundos que dificulten la integración con agentes y cuadernos de IA, el repositorio implementa una **estructura plana particionada por prefijos de dominio**.

* **Separación de Responsabilidades:** Cada archivo aborda un único aspecto del ciclo de vida de la infraestructura.
* **Agrupamiento Léxico:** El prefijo garantiza que los archivos relacionados se ordenen contiguamente en cualquier explorador estándar.
* **Enrutamiento Directo:** Permite referenciar cualquier documento mediante rutas relativas simples sin colisiones de nombres.

---

## 2. Dominios Funcionales del Repositorio

| Prefijo | Dominio Conceptual | Alcance y Responsabilidad |
| :--- | :--- | :--- |
| **`docs_`** | Arquitectura & Gobernanza | Blueprints de red, diseño de subredes/VLANs, topología y directrices globales. |
| **`inventory_`** | Inventario & Estado | Catálogo de activos físicos, interfaces de red, asignación de IPs/MACs y snapshots. |
| **`sec_`** | Seguridad & Policiamiento | Matrices de filtrado inter-VLAN, políticas Zero-Trust, VPNs y modelos de amenaza. |
| **`ops_`** | Operaciones & Resiliencia | Bitácora de cambios (Changelog), políticas de copia de seguridad 3-2-1 y runbooks de DR. |
| **`config_`** | Configuraciones Declarativas | Ajustes específicos de switches, routers, reglas de firewall, certificados y DNS. |
| **`lab_`** | Laboratorio & Pruebas | Experimentos en hipervisores (Proxmox / Phoenix-Core), clústeres K3s y PoCs. |
| **`tasks_`** | Gestión & Roadmap | Backlog de tareas de ingeniería, mejoras pendientes e hitos de evolución. |
| **`diagrams_`** | Topología Visual | Esquemas gráficos de distribución física, mapas lógicos y matrices de zonas. |
| **`reviews_`** | Auditoría & Reportes | Informes trimestrales de estado, revisiones de salud y análisis de vulnerabilidades. |
| **`archive_`** | Histórico & Deprecados | Documentación de equipos retirados o topologías anteriores preservadas para trazabilidad. |

> Para conocer la gramática exacta de construcción de nombres de archivo y entidades, consulta [docs_naming_conventions.md](docs_naming_conventions.md).

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
├── reviews_quarterly_2026-Q3.md
├── reviews_security_2026-08.md
├── archive_old_wifi_topology_2024.md
└── archive_previous_blueprint.md
```

---

## 📝 Control de Cambios y Autoría

* **Autor:** Richie
* **Fecha de última actualización:** 2026-08-16
* **Versión del documento:** 1.0.0
