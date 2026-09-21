# Adaptación de Estándares Tradicionales de Calidad (CMMI y MoProSoft) a GitHub y Open Hub Tec

> **Asignatura:** Gestión de Proyectos de Software  
> **Institución:** Instituto Tecnológico de Tlaxiaco (Sistemas Tec Tlaxiaco)  
> **Equipo:** Grupo 4  
> **Criterio Evaluado:** Indicador A: Adaptación a situaciones y contextos complejos (Valor: 5.0 pts — Rango Excelente: 4.8 – 5.0)

---

## 1. El Conflicto Entre Modelos Tradicionales y el Desarrollo Ágil Abierto

Los modelos clásicos de calidad de software como **CMMI-DEV v2.0** (concebido originalmente por el *Software Engineering Institute* para contratistas de defensa) y **MoProSoft / NMX-I-059-NYCE** (la norma mexicana de calidad para la industria del software) establecieron las bases de la ingeniería de software moderna: repetibilidad, control de configuración, trazabilidad y aseguramiento formal.

Sin embargo, en su aplicación convencional, estos marcos presentan una severa fricción con el desarrollo contemporáneo de código abierto:
* **Burocracia Documental:** Exigen carpetas físicas o formatos ofimáticos extensos que no residen junto al código fuente.
* **Comités Centralizados de Control de Cambios (CCB):** Mecanismos de aprobación lentos y presenciales que paralizan el flujo de entrega continua.
* **Falta de Automatización:** Auditorías manuales retrospectivas que detectan defectos semanas después de haber sido introducidos al repositorio.

El reto superado por el Grupo 4 radica en **traducir los principios esenciales de CMMI y MoProSoft a artefactos nativos, ejecutables y automatizados dentro del ecosistema GitHub y el marco Open Hub Tec del Tecnológico Nacional de México**, adaptándolos a las exigencias de un proyecto para la Región Mixteca.

```
+---------------------------------------------------------------------------------------------------+
|               TRADUCCIÓN DE ESTÁNDARES TRADICIONALES A PRIMITIVAS DE GITHUB                       |
|                                                                                                   |
|  [CMMI-DEV v2.0 / MoProSoft]           [Transformación Open Hub Tec]       [Primitiva GitHub]     |
|  * Gestión de Configuración (CM/GSO) -> Convención estricta de ramas y commits -> Conventional Git|
|  * Comité de Control de Cambios (CCB) -> Aprobación formal entre pares (Review) -> Pull Request    |
|  * Trazabilidad de Requerimientos    -> Enlace bidireccional Issue <-> Commit -> Issues Templates  |
|  * Aseguramiento de Calidad (PPQA)   -> Auditoría automatizada continua       -> GitHub Actions    |
|  * Medición y Análisis (MA)          -> Scorecard cuantitativo e Insignias    -> audit_tool.py     |
+---------------------------------------------------------------------------------------------------+
```

---

## 2. Mapeo Sistemático CMMI-DEV v2.0 a GitHub

A continuación, se detalla la correspondencia entre las Áreas de Práctica de **CMMI-DEV v2.0** y su implementación operativa en este repositorio:

### 2.1. Gestión de la Configuración (Configuration Management - CM)
* **Objetivo CMMI:** Establecer y mantener la integridad de los productos de trabajo mediante la identificación, control de cambios y auditorías de línea base.
* **Adaptación a GitHub:**
  * **Identificación de Elementos de Configuración:** Definición explícita de artefactos versionados frente a artefactos volátiles mediante el archivo `.gitignore`.
  * **Líneas Base (*Baselines*):** Cada versión estable se congela mediante etiquetas criptográficas firmadas en Git (*Git Semantic Tags*, ej. `v1.0.0`).
  * **Control de Modificaciones:** Se prohíbe el *commit* directo sobre ramas de producción (`main`/`master`); todo cambio debe provenir de una rama temática (`feature/`, `bugfix/`) validada por el template formal de Pull Request.

### 2.2. Gestión de Requerimientos (Requirements Management - REQM)
* **Objetivo CMMI:** Gestionar los requerimientos de los productos y componentes del producto e identificar las inconsistencias entre los requerimientos y los planes y productos de trabajo del proyecto.
* **Adaptación a GitHub:**
  * **Estructura Formal:** Plantillas de Issue para requerimientos (`.github/ISSUE_TEMPLATE/feature_request.md`) vinculadas obligatoriamente a las Historias de Usuario (US-01 a US-05).
  * **Matriz de Trazabilidad Bidireccional:** Todo mensaje de commit incluye el código del Criterio de Aceptación (ej. `feat(us-01): implementar hash local SHA-256 (CA-1.1)`), permitiendo rastrear el origen de cada línea de código hasta el requerimiento del usuario comunal.

### 2.3. Verificación y Validación (Verification & Validation - VER / VAL)
* **Objetivo CMMI:** Asegurar que los productos de trabajo seleccionados cumplen con los requerimientos especificados (Verificación) y que el producto cumple con su uso previsto en su entorno operativo real (Validación).
* **Adaptación a GitHub:**
  * **Verificación Automatizada:** Ejecución de suites de prueba y linters en el pipeline de GitHub Actions (`.github/workflows/audit.yml`) antes de permitir el merge.
  * **Validación Territorial (Mixteca Gate):** Lista de verificación en el Pull Request que evalúa la capacidad del cambio de operar en modo *Offline-First* con conectividad 2G y baja memoria RAM.

### 2.4. Aseguramiento de la Calidad del Proceso y del Producto (PPQA)
* **Objetivo CMMI:** Proporcionar al personal y a la gerencia una visión objetiva de los procesos y de los productos de trabajo asociados.
* **Adaptación a GitHub:**
  * Implementación de la herramienta de auditoría automatizada `scripts/audit_tool.py`, la cual evalúa el repositorio contra la matriz de calidad y genera de forma imparcial el dictamen oficial de insignia.

---

## 3. Mapeo con la Norma Mexicana MoProSoft (NMX-I-059-NYCE)

MoProSoft estructura los procesos de una organización de software en tres niveles. El repositorio adapta específicamente los procesos del **Nivel Operación**:

| Proceso MoProSoft | Propósito Tradicional | Implementación Adaptada en el Repositorio Grupo 4 |
| :--- | :--- | :--- |
| **GSO - Gestión de la Configuración del Software** | Mantener la integridad de los productos del proyecto durante todo el ciclo de vida. | Control de versiones distribuido, historial limpio de commits convencionales y licenciamiento MIT explícito. |
| **DTM - Desarrollo y Mantenimiento de Software** | Realizar las actividades de análisis, diseño, construcción, integración y pruebas de software. | Lista de verificación pre-integración (`LISTA_DE_VERIFICACION.md`) y plantilla de Pull Request con pruebas obligatorias. |
| **VER - Verificación y Validación** | Comprobar que los productos de trabajo satisfacen sus especificaciones. | Pipeline CI/CD en GitHub Actions y reporte periódico de auditoría (`AUDITORIA_INFORME.md`). |

---

## 4. Complejidad Técnica y Contexto Open Hub Tec

La iniciativa **Open Hub Tec** del Tecnológico Nacional de México promueve que los proyectos de los institutos tecnológicos alcancen estándares de calidad de nivel internacional sin perder su vocación social y pertinencia regional.

### 4.1. El Reto de la Complejidad en Proyectos Abiertos Estudiantiles
Un proyecto de código abierto desarrollado por estudiantes universitarios enfrenta riesgos singulares:
1. **Rotación de Integrantes:** El fin del ciclo escolar suele provocar la pérdida de conocimiento tácito del proyecto. La formalización mediante plantillas y listas de verificación de CMMI/MoProSoft garantiza que cualquier nuevo estudiante del IT Tlaxiaco pueda retomar el repositorio sin fricción.
2. **Ausencia de Servidores Comerciales:** Al no contar con licencias de herramientas privativas de auditoría (como SonarQube Enterprise o Jira Server), la herramienta desarrollada en Python (`scripts/audit_tool.py`) provee un **motor de auditoría autónomo, gratuito y portátil** que se ejecuta tanto en la laptop más modesta como en la nube gratuita de GitHub Actions.
3. **Restricciones del Entorno Comunal:** Los modelos tradicionales de calidad nunca contemplaron la operación en celdas telefónicas 2G o bajo asambleas indígenas. Nuestra adaptación añade dimensiones de calidad específicas (Frugalidad de datos, privacidad defensiva de testigos, ausencia de puertas traseras de administración), enriqueciendo la norma MoProSoft con pertinencia comunitaria oaxaqueña.

---

## 5. Conclusiones del Marco de Adaptación

La adaptación de CMMI y MoProSoft a GitHub demuestra que:
* **El rigor metodológico no está reñido con la agilidad:** Al codificar las reglas de calidad en scripts y plantillas de GitHub, el cumplimiento normativo deja de ser una carga burocrática y se convierte en un acelerador de la calidad del software.
* **El software universitario adquiere grado profesional:** Los estudiantes aplican en la práctica estándares internacionales de ingeniería, preparando al Instituto Tecnológico de Tlaxiaco como un referente en el desarrollo de software confiable para la sociedad.
