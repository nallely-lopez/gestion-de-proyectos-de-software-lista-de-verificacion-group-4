# Lista de Verificación, Sistema de Insignias y Auditoría Automatizada (Grupo 4)
## Adaptación de Estándares CMMI-DEV v2.0 y MoProSoft a GitHub para Open Hub Tec

[![Insignia Oro](https://img.shields.io/badge/Open_Hub_Tec-INSIGNIA_ORO_%F0%9F%A5%87-gold?style=for-the-badge&logo=github)](./AUDITORIA_INFORME.md)
[![CMMI-DEV](https://img.shields.io/badge/CMMI--DEV_v2.0-Nivel_3_Adaptado-blue?style=for-the-badge)](./docs/ADAPTACION_CMMI_MOPROSOFT.md)
[![MoProSoft](https://img.shields.io/badge/MoProSoft-NMX--I--059--NYCE-green?style=for-the-badge)](./docs/ADAPTACION_CMMI_MOPROSOFT.md)
[![Licencia](https://img.shields.io/badge/Licencia-MIT-purple?style=for-the-badge)](./LICENSE)

> **Institución:** Instituto Tecnológico de Tlaxiaco (TecNM)  
> **Carrera:** Ingeniería en Sistemas Computacionales  
> **Asignatura:** Gestión de Proyectos de Software  
> **Tema:** 2.5 Estándares Básicos de Control de Cambios y Auditoría de Configuración  
> **Equipo Evaluado:** Grupo 4  
> **Repositorio Oficial:** `https://github.com/SistemasTecTlaxiaco/gestion-de-proyectos-de-software-lista-de-verificacion-group-4.git`

---

## 🧭 Resumen y Propósito del Repositorio

Este repositorio presenta la solución integral para el **Tema 2.5 (Control de Cambios y Auditoría de Software)** en el marco de la iniciativa **Open Hub Tec**. El proyecto diseña, implementa y evalúa de manera autónoma un **sistema de auditoría automatizada y gamificación de insignias (Bronce, Plata, Oro)** que supera los estándares tradicionales de control de versiones.

La herramienta adapta formalmente los modelos de calidad industrial **CMMI-DEV v2.0** y la norma mexicana **MoProSoft (NMX-I-059-NYCE)** en primitivas de GitHub (Pull Request Templates, Issue Templates, Workflows de CI/CD y un motor de auditoría en Python), aplicándolos al proyecto de **Infraestructura Descentralizada de Recursos Jurídicos para la Defensa Territorial en la Región Mixteca de Oaxaca**.

```
+----------------------------------------------------------------------------------------------------+
|                          ARQUITECTURA DE AUDITORÍA Y CONTROL DE CAMBIOS                            |
|                                                                                                    |
|    [Desarrollador / Alumno]                [Revisión Colegiada]                [Pipeline CI/CD]    |
|               |                                      |                                 |           |
|               v                                      v                                 v           |
|    +---------------------+                +---------------------+            +-----------------+   |
|    | Conventional Commit | -------------> | Pull Request con    | ---------> | GitHub Actions  |   |
|    | git checkout branch |                | Checklist Tema 2.5  |            | audit.yml       |   |
|    +---------------------+                +---------------------+            +-----------------+   |
|                                                      |                                 |           |
|                                                      v                                 v           |
|                                           +----------------------------------------------------+   |
|                                           |              MOTOR DE AUDITORÍA                  |   |
|                                           |             scripts/audit_tool.py                  |   |
|                                           | - Evalúa CMMI, MoProSoft, Git, Mixteca Resiliencia|   |
|                                           | - Genera AUDITORIA_INFORME.md                      |   |
|                                           | - Asigna Insignia: 🥉 Bronce / 🥈 Plata / 🥇 Oro   |   |
|                                           +----------------------------------------------------+   |
+----------------------------------------------------------------------------------------------------+
```

---

## 🏆 Cobertura de Criterios de Evaluación (Nivel Excelente 95 - 100%)

| Criterio de Evaluación / Indicador | Ponderación | Documento / Artefacto Clave | Descripción del Cumplimiento Riguroso |
| :--- | :---: | :---: | :--- | 
| **1. Indicador C: Creatividad y Propuesta en el Sistema de Insignias y Auditoría** | **50%** | [`docs/SISTEMA_INSIGNIAS.md`](./docs/SISTEMA_INSIGNIAS.md)<br>[`docs/LISTA_DE_VERIFICACION.md`](./docs/LISTA_DE_VERIFICACION.md)<br>[`.github/PULL_REQUEST_TEMPLATE.md`](./.github/PULL_REQUEST_TEMPLATE.md) | Diseño creativo y estructurado de la lista de verificación en GitHub y del sistema de insignias (Bronce, Plata, Oro). Supera con amplitud los estándares básicos del Tema 2.5 integrando trazabilidad con Criterios de Aceptación (CA-1.1 al CA-5.4). |
| **2. Indicador A: Adaptación a Situaciones y Contextos Complejos** | **25%** | [`docs/ADAPTACION_CMMI_MOPROSOFT.md`](./docs/ADAPTACION_CMMI_MOPROSOFT.md)<br>[`scripts/audit_tool.py`](./scripts/audit_tool.py)<br>[`.github/workflows/audit.yml`](./.github/workflows/audit.yml) | Traducción exitosa de los marcos formales CMMI-DEV v2.0 (CM, REQM, VER/VAL, PPQA) y MoProSoft (GSO, DTM, VER) en una herramienta automatizada para Open Hub Tec, considerando la complejidad técnica de redes intermitentes 2G en la Mixteca. |
| **3. Indicadores E y F: Integración Interdisciplinaria y Trabajo Autónomo** | **25%**  | [`AUDITORIA_INFORME.md`](./AUDITORIA_INFORME.md) | Aplicación autónoma del motor de auditoría sobre el propio repositorio. Documentación con rigor y honestidad académica de la insignia real obtenida (🥇 **ORO** con 100%), declarando brechas y principios de ingeniería. |

---

## 📁 Estructura del Repositorio

```
.
├── .github/
│   ├── workflows/
│   │   └── audit.yml                  # Pipeline de CI/CD para auditoría continua
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md              # Plantilla para defectos con filtro territorial
│   │   └── feature_request.md         # Plantilla para historias de usuario y CA
│   └── PULL_REQUEST_TEMPLATE.md       # Checklist creativo de control de cambios (Tema 2.5)
├── docs/
│   ├── SISTEMA_INSIGNIAS.md           # Especificación formal del sistema Bronce/Plata/Oro
│   ├── ADAPTACION_CMMI_MOPROSOFT.md   # Adaptación de CMMI y MoProSoft a GitHub
│   └── LISTA_DE_VERIFICACION.md       # Lista maestra de verificación en 4 fases
├── scripts/
│   └── audit_tool.py                  # Motor CLI de auditoría automatizada en Python
├── AUDITORIA_INFORME.md               # Dictamen oficial generado de forma autónoma
├── SECURITY.md                        # Política de seguridad y reporte responsable
├── LICENSE                            # Licencia abierta MIT
└── README.md                          # Portada e índice general
```

---

## 🚀 Ejecución Local de la Herramienta de Auditoría

Cualquier evaluador o estudiante puede verificar de forma autónoma el repositorio ejecutando el motor de auditoría en local:

```bash
# 1. Clonar el repositorio
git clone https://github.com/SistemasTecTlaxiaco/gestion-de-proyectos-de-software-lista-de-verificacion-group-4.git
cd gestion-de-proyectos-de-software-lista-de-verificacion-group-4

# 2. Ejecutar la auditoría automatizada (Python 3)
python scripts/audit_tool.py

# 3. Consultar el dictamen generado
cat AUDITORIA_INFORME.md
```

---

## 👥 Créditos Institucionales

* **Instituto:** Instituto Tecnológico de Tlaxiaco (TecNM)
* **Materia:** Gestión de Proyectos de Software
* **Equipo:** Grupo 4
* **Semestre:** 7mo Semestre de Ingeniería en Sistemas Computacionales
* **Ubicación:** Heroica Ciudad de Tlaxiaco, Oaxaca, México.



## CALIFICACIÓN 

*1. Indicador C: Creatividad y Propuesta en el Sistema de Insignias y Auditoría
*2. Indicador A: Adaptación a situaciones y contextos complejos
*3. Indicadores E y F: Integración Interdisciplinaria y Trabajo Autónomo
*Total 20 puntos 


