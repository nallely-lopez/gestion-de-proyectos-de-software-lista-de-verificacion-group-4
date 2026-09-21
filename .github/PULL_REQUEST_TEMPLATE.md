## 📋 Solicitud de Cambio (Pull Request) — Grupo 4
> **Proyecto:** Infraestructura de Defensa Territorial Descentralizada (Región Mixteca)  
> **Asignatura:** Gestión de Proyectos de Software — Instituto Tecnológico de Tlaxiaco  
> **Tema:** 2.5 Estándares de Control de Cambios y Auditoría de Configuración

---

### 1. 🎯 Propósito y Contexto del Cambio
* **Historia de Usuario Vinculada:**
  - [ ] US-01: Registro e inmutabilidad de recursos jurídicos
  - [ ] US-02: Consulta y filtrado seguro de precedentes
  - [ ] US-03: Publicación anónima protegida (DID)
  - [ ] US-04: Respaldo y validación comunitaria (Web of Trust)
  - [ ] US-05: Sincronización local y acceso sin conexión
  - [ ] Mantenimiento General / Documentación
* **Número de Issue / Ticket:** Closes #
* **Tipo de Cambio (Conventional Commits):**
  - [ ] `feat`: Nueva funcionalidad técnica
  - [ ] `fix`: Corrección de un defecto reportado
  - [ ] `docs`: Modificación o adición de documentación técnica
  - [ ] `refactor`: Mejora de estructura sin alterar comportamiento
  - [ ] `test`: Adición o ajuste de suites de prueba
  - [ ] `chore` / `ci`: Mantenimiento de configuración o pipelines

---

### 2. 🛡️ Lista de Verificación de Calidad (Tema 2.5 & CMMI/MoProSoft)

Marque con una `[x]` las casillas verificadas antes de solicitar la integración:

#### A. Control de Configuración y Código (CMMI-CM / MoProSoft GSO)
- [ ] **Nomenclatura de Rama:** La rama sigue el estándar (`feature/US-xx`, `bugfix/issue-xx`, `docs/tema-xx`).
- [ ] **Conventional Commits:** Todos los mensajes de commit respetan el formato canónico (`tipo(ámbito): descripción`).
- [ ] **Historial Limpio:** No se incluyen archivos temporales, binarios generados ni dependencias (`.gitignore` respetado).
- [ ] **Trazabilidad:** Se enlaza de forma explícita el commit con el criterio de aceptación correspondiente (CA-x.x).

#### B. Pruebas y Validación Técnica (CMMI-VER / CMMI-VAL)
- [ ] **Pruebas Unitarias Locales:** Ejecutadas con 100% de aprobación (`cargo test` o `npm test`).
- [ ] **Análisis Estático (Linting):** Cero advertencias críticas reportadas (`clippy`, `eslint` o linter aplicable).
- [ ] **Compilación Determinista:** El código compila sin advertencias en entorno limpio local.

#### C. Filtro de Resiliencia Territorial (Región Mixteca)
- [ ] **Resiliencia Offline-First:** La funcionalidad opera o degrada suavemente sin conexión a Internet.
- [ ] **Frugalidad de Datos:** La carga útil de sincronización se mantiene optimizada (< 25 KB).
- [ ] **Purga de Privacidad (PII):** No se filtran metadatos personales, nombres de testigos, números IP ni coordenadas sensibles.
- [ ] **Bajo Consumo de Batería:** No se ejecutan bucles infinitos de sondeo (*polling*) en segundo plano.

---

### 3. 🏅 Impacto en el Sistema de Insignias Open Hub Tec
Este cambio contribuye a mantener o elevar la insignia del repositorio:
- [ ] **Nivel Bronce:** Cumplimiento estricto de control de versiones y plantillas.
- [ ] **Nivel Plata:** Cobertura de pruebas automáticas y pase de análisis estático en CI/CD.
- [ ] **Nivel Oro:** Verificación formal de invariantes, auditoría de seguridad aprobada y resiliencia offline demostrada.

---

### 4. 👥 Aprobación de Pares (Peer Review)
* **Revisor Principal (Estudiante):** @
* **Dictamen del Revisor:**
  - [ ] Aprobado para integración en rama principal (`main`/`master`)
  - [ ] Requiere ajustes señalados en comentarios
