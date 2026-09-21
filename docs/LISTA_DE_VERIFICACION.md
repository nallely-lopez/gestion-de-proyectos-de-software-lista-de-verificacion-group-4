# Lista Maestra de Verificación de Calidad y Control de Cambios (Tema 2.5)

> **Asignatura:** Gestión de Proyectos de Software  
> **Institución:** Instituto Tecnológico de Tlaxiaco (Sistemas Tec Tlaxiaco)  
> **Equipo:** Grupo 4  
> **Referencia Normativa:** CMMI-DEV v2.0 (CM/VER/VAL) & MoProSoft (GSO/DTM)

---

## 1. Introducción y Propósito

La presente **Lista de Verificación (Checklist)** constituye el instrumento operativo central para la gestión y auditoría del control de cambios en el proyecto. Ninguna modificación técnica puede ser integrada a la línea base del sistema sin haber superado las puertas de calidad (*quality gates*) aquí descritas.

---

## 2. Fases de la Lista de Verificación

```
[Fase 1: Pre-Desarrollo] ---> [Fase 2: Construcción y Commit] ---> [Fase 3: Pre-Integración (PR)] ---> [Fase 4: Auditoría y Release]
```

---

### Fase 1: Pre-Desarrollo (Definición y Trazabilidad de Requerimientos)
*Objetivo: Asegurar que todo trabajo responde a una necesidad legítima validada por la comunidad y el cliente.*

| Código | Punto de Control | Responsable | Criterio de Aprobación |
| :---: | :--- | :---: | :--- |
| **CK-1.1** | Existencia de Issue o Historia de Usuario | Desarrollador | Existe un Issue formal en GitHub vinculado a US-01, US-02, US-03, US-04 o US-05. |
| **CK-1.2** | Identificación de Criterios de Aceptación (CA) | Desarrollador | Se especifica con exactitud qué criterios (ej. CA-1.1, CA-5.2) serán satisfechos. |
| **CK-1.3** | Creación de Rama Temática Aislada | Desarrollador | La rama parte de `main` actualizada y sigue la convención: `feature/<nombre>`, `fix/<nombre>`, `docs/<nombre>`. |

---

### Fase 2: Construcción y Commit (Disciplina de Configuración Local)
*Objetivo: Garantizar la higiene del repositorio y la legibilidad histórica del desarrollo.*

| Código | Punto de Control | Responsable | Criterio de Aprobación |
| :---: | :--- | :---: | :--- |
| **CK-2.1** | Respeto Estricto de `.gitignore` | Desarrollador | `git status` no reporta binarios, `.env`, llaves privadas, carpetas de compilación ni volcados de base de datos. |
| **CK-2.2** | Formato de Conventional Commits | Desarrollador | Cada commit utiliza prefijos estandarizados: `feat:`, `fix:`, `docs:`, `test:`, `refactor:`, `chore:`. |
| **CK-2.3** | Atomicidad del Commit | Desarrollador | Cada commit resuelve una unidad lógica de cambio; no se mezclan refactorizaciones cosméticas con cambios lógicos. |
| **CK-2.4** | Compilación y Pruebas Locales Exitosas | Desarrollador | El proyecto compila limpiamente y todas las pruebas locales pasan al 100%. |

---

### Fase 3: Pre-Integración y Pull Request (Revisión de Pares y CI/CD)
*Objetivo: Control colegiado de cambios conforme al modelo de Comités de Control de Cambios (CCB).*

| Código | Punto de Control | Responsable | Criterio de Aprobación |
| :---: | :--- | :---: | :--- |
| **CK-3.1** | Diligenciamiento de Plantilla de PR | Desarrollador | Se completan todos los campos obligatorios de `.github/PULL_REQUEST_TEMPLATE.md`. |
| **CK-3.2** | Aprobación del Pipeline Automatizado | CI / Actions | El workflow de GitHub Actions (`audit.yml`) finaliza con estado exitoso (verde). |
| **CK-3.3** | Verificación de Resiliencia Mixteca | Revisor (Peer) | Se valida que el cambio no rompe la capacidad Offline-First ni incrementa el consumo de datos de forma innecesaria. |
| **CK-3.4** | Purga Criptográfica de Privacidad | Revisor (Peer) | Se inspecciona que no se introduzcan fugas de datos personales, IPs o telemetría que exponga a los defensores. |
| **CK-3.5** | Aprobación Mínima de Pares | Revisor (Peer) | Al menos un integrante del equipo firma la aprobación formal del Pull Request. |

---

### Fase 4: Auditoría y Línea Base (Liberación e Insignias)
*Objetivo: Certificar la madurez del software y actualizar la insignia oficial del repositorio.*

| Código | Punto de Control | Responsable | Criterio de Aprobación |
| :---: | :--- | :---: | :--- |
| **CK-4.1** | Ejecución de `audit_tool.py` | Líder de QA | Se ejecuta la herramienta de auditoría automatizada y se regenera el dictamen formal. |
| **CK-4.2** | Umbral de Insignia Garantizado | Líder de QA | El puntaje global se mantiene por encima del umbral requerido (Bronce: >=60%, Plata: >=75%, Oro: >=90%). |
| **CK-4.3** | Integración sin Fricción a Rama Principal | Release Manager | Se realiza el merge mediante estrategia *Squash & Merge* o *Rebase* preservando un grafo lineal y limpio. |
| **CK-4.4** | Etiquetado de Versión (SemVer) | Release Manager | Se emite un tag Git anotado (ej. `v1.0.0`) respaldando la nueva línea base aprobada. |

---

## 3. Matriz de Aplicabilidad por Nivel de Insignia

| Nivel de Insignia | Puntos de Control Obligatorios | Estado de Verificación |
| :--- | :--- | :---: |
| 🥉 **Bronce** | CK-1.1 al CK-2.4 (Fase 1 y Fase 2 completas) | **Superado** |
| 🥈 **Plata** | Todo Bronce + CK-3.1 al CK-3.5 (Fase 3 completa con CI/CD) | **Superado** |
| 🥇 **Oro** | Todo Plata + CK-4.1 al CK-4.4 (Fase 4 completa con auditoría formal) | **Superado** |
