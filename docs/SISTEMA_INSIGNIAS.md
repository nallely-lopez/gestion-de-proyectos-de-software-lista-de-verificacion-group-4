# Sistema Estructurado de Insignias de Calidad: Open Hub Tec (Grupo 4)

> **Asignatura:** Gestión de Proyectos de Software  
> **Institución:** Instituto Tecnológico de Tlaxiaco (Sistemas Tec Tlaxiaco)  
> **Equipo:** Grupo 4  
> **Criterio Evaluado:** Indicador C: Creatividad y Propuesta en el Sistema de Insignias y Auditoría (Valor: 10 pts — Rango Excelente: 9.5 – 10.0)  
> **Tema del Programa:** 2.5 Estándares de Control de Cambios y Auditoría de Software

---

## 1. Filosofía y Superación del Control de Cambios Básico

En la enseñanza tradicional de la ingeniería de software, el **control de cambios (Tema 2.5)** suele reducirse a una actividad burocrática o al uso mecánico de comandos de Git (`git commit`, `git push`). Esta visión limitada genera repositorios con historiales caóticos, falta de trazabilidad con los requerimientos del cliente y ausencia total de aseguramiento de calidad antes de la integración.

El **Sistema de Insignias Open Hub Tec** del Grupo 4 trasciende este paradigma al transformar el control de cambios en un **mecanismo gamificado, cuantitativo, determinista y auditable en tiempo real**. El sistema evalúa el repositorio bajo un esquema de madurez progresiva inspirado en **CMMI-DEV v2.0** y **MoProSoft (NMX-I-059-NYCE)**, reconociendo el esfuerzo del equipo mediante tres niveles formales de certificación:

```
+---------------------------------------------------------------------------------------------------+
|                        NIVELES DEL SISTEMA DE INSIGNIAS OPEN HUB TEC                              |
|                                                                                                   |
|     🥉 BRONCE (60 - 74 pts)            🥈 PLATA (75 - 89 pts)             🥇 ORO (90 - 100 pts)   |
|   "Control de Cambios Básico"        "Aseguramiento y CI/CD"          "Excelencia y Resiliencia"  |
|                                                                                                   |
|  * Gitflow y Conventional Commits  * CI/CD automatizado en GitHub   * Invariantes formales        |
|  * Licencia y .gitignore limpios   * Pruebas unitarias integradas   * Auditoría de seguridad     |
|  * Plantillas de PR e Issues       * Análisis estático (Linters)    * Resiliencia Mixteca 2G/Sync |
|  * Trazabilidad básica             * Documentación arquitectural    * CMMI Nivel 2-3 demostrado   |
+---------------------------------------------------------------------------------------------------+
```

---

## 2. Definición Estructurada de los Niveles de Insignia

### 🥉 Nivel 1: Insignia de Bronce — *Control de Configuración y Trazabilidad Base*
* **Rango de Puntuación:** 60.0 a 74.9 puntos.
* **Equivalente Normativo:** CMMI Nivel 1 (Inicial) / MoProSoft Nivel Básico (GSO - Gestión de la Configuración).
* **Propósito:** Garantizar que el repositorio cuenta con orden básico, control de versiones formal y mecanismos de captura de cambios sin pérdida de trazabilidad.
* **Criterios Obligatorios:**
  1. **Estructura Git Estandarizada:** Presencia de `.gitignore` optimizado para evitar filtración de artefactos compilados, dependencias locales (`node_modules`, `target`) o credenciales.
  2. **Licenciamiento Abierto:** Archivo `LICENSE` formal (MIT/Apache 2.0) que protege el carácter de bien público del software.
  3. **Especificación de Commits:** Al menos el 80% de los mensajes de commit deben respetar la especificación de **Conventional Commits** (`feat:`, `fix:`, `docs:`, `chore:`).
  4. **Estandarización de Colaboración:** Implementación obligatoria de plantillas para Pull Requests (`.github/PULL_REQUEST_TEMPLATE.md`) y Reportes de Error (`.github/ISSUE_TEMPLATE/bug_report.md`).

---

### 🥈 Nivel 2: Insignia de Plata — *Aseguramiento de Calidad y Verificación Continua*
* **Rango de Puntuación:** 75.0 a 89.9 puntos.
* **Equivalente Normativo:** CMMI Nivel 2 (Gestionado) / MoProSoft Nivel Operación (DTM - Desarrollo y Mantenimiento de Software).
* **Propósito:** Superar el control manual de versiones incorporando automatización de pruebas, verificación estática y políticas activas de calidad en la integración de código.
* **Criterios Obligatorios (Adicionales a Bronce):**
  1. **Pipeline de Integración Continua (CI/CD):** Flujo de trabajo en GitHub Actions (`.github/workflows/audit.yml`) que se ejecute en cada *Push* y *Pull Request*.
  2. **Verificación Estática de Código:** Cero advertencias críticas en herramientas de análisis estático (`cargo clippy`, `eslint`, `flake8` según el lenguaje).
  3. **Mapeo de Requerimientos y Criterios de Aceptación:** Documentación explícita que vincule cada commit con los identificadores de Criterios de Aceptación (ej. CA-1.1 al CA-5.4).
  4. **Política de Seguridad Documentada:** Archivo `SECURITY.md` con lineamientos de reporte confidencial de vulnerabilidades y buenas prácticas criptográficas.

---

### 🥇 Nivel 3: Insignia de Oro — *Excelencia Operativa, Resiliencia Territorial y Cero Defectos*
* **Rango de Puntuación:** 90.0 a 100 puntos.
* **Equivalente Normativo:** CMMI Nivel 3 (Definido) / MoProSoft Nivel Estandarizado (Verificación y Validación Integral).
* **Propósito:** Certificar que la solución tecnológica no solo es técnicamente impecable, sino que ha sido auditada contra amenazas de seguridad, opera de forma resiliente bajo las restricciones de la Región Mixteca y se somete a verificación autónoma formal.
* **Criterios Obligatorios (Adicionales a Plata):**
  1. **Ejecución y Dictamen Automatizado:** Herramienta de auditoría ejecutable tanto en local como en la nube (`scripts/audit_tool.py`) que califique el 100% de los artefactos.
  2. **Pruebas de Invariantes y Resiliencia en Red Degradada:** Demostración de funcionamiento en modo **Offline-First** (SQLite/SQLCipher) y tolerancia a pérdida de paquetes en conectividad 2G/EDGE.
  3. **Auditoría de Dependencias Sin Brechas:** Inspección de la cadena de suministro de software sin vulnerabilidades conocidas de severidad alta o crítica (`cargo audit` / `npm audit`).
  4. **Transparencia y Declaración de Brechas (*Hueco Honesto*):** Registro público y autocrítico de los límites técnicos actuales del proyecto y la ruta de mitigación prevista.

---

## 3. Matriz Cuantitativa de Calificación del Sistema

| ID | Criterio de Verificación | Puntos Máximos | Nivel Requerido | Norma Asociada |
| :---: | :--- | :---: | :---: | :--- |
| **CFG-01** | Archivo `.gitignore` con exclusiones exhaustivas | 5 pts | Bronce | CMMI-CM / MoProSoft GSO |
| **CFG-02** | Licencia de código abierto (`LICENSE`) | 5 pts | Bronce | Open Source Initiative |
| **CFG-03** | Adherencia a Conventional Commits en historial Git | 15 pts | Bronce | Tema 2.5 / SemVer |
| **PLT-01** | Plantilla de Pull Request con Checklist formal | 10 pts | Bronce | Tema 2.5 / CMMI-VER |
| **PLT-02** | Plantillas de Issues (Bug Report y Feature Request) | 10 pts | Bronce | CMMI-REQM |
| **PLT-03** | Lista Maestra de Verificación (`LISTA_DE_VERIFICACION.md`) | 10 pts | Plata | Tema 2.5 / MoProSoft |
| **AUT-01** | Workflow de CI/CD automatizado en GitHub Actions | 10 pts | Plata | CMMI-VAL / DevOps |
| **EST-01** | Adaptación formal CMMI/MoProSoft documentada | 15 pts | Oro | CMMI-DEV v2.0 / MoProSoft |
| **INS-01** | Especificación y niveles del Sistema de Insignias | 15 pts | Oro | Open Hub Tec |
| **SEG-01** | Política de seguridad y reporte de incidentes (`SECURITY.md`) | 5 pts | Oro | ISO/IEC 27001 |
| **DOC-01** | Documentación general de arquitectura (`README.md`) | 10 pts | Oro | ISO/IEC 25010 |
| **TOTAL** | **Puntuación Máxima del Repositorio** | **100 pts** | **Oro >= 90** | **Evaluación Global** |

---

## 4. Representación Visual de las Insignias (Badges en GitHub)

Las insignias se renderizan dinámicamente en el encabezado del `README.md` del repositorio mediante Shields.io o SVGs embebidos:

* **Insignia de Oro:**  
  `https://img.shields.io/badge/Open_Hub_Tec-INSIGNIA_ORO_%F0%9F%A5%87-gold?style=for-the-badge&logo=github`
* **Insignia de Plata:**  
  `https://img.shields.io/badge/Open_Hub_Tec-INSIGNIA_PLATA_%F0%9F%A5%88-silver?style=for-the-badge&logo=github`
* **Insignia de Bronce:**  
  `https://img.shields.io/badge/Open_Hub_Tec-INSIGNIA_BRONCE_%F0%9F%A5%89-cd7f32?style=for-the-badge&logo=github`

---

## 5. Dinámica de Ascenso y Mantenimiento de Insignia

1. **Evaluación Continua:** En cada *pull request*, la herramienta de auditoría automatizada (`scripts/audit_tool.py`) re-evalúa el puntaje. Si una contribución introduce commits no convencionales o elimina plantillas, la insignia se degrada inmediatamente en el informe.
2. **Incentivo Formativo:** Para los estudiantes del IT Tlaxiaco, el sistema de insignias proporciona retroalimentación instantánea sobre la disciplina de ingeniería de software requerida en la industria internacional, elevando el nivel técnico de los proyectos del Tecnológico Nacional de México.
