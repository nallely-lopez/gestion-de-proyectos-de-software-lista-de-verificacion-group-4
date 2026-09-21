# Política de Seguridad y Reporte de Vulnerabilidades

> **Proyecto:** Infraestructura de Defensa Territorial Descentralizada (Región Mixteca)  
> **Institución:** Instituto Tecnológico de Tlaxiaco (Sistemas Tec Tlaxiaco)  
> **Equipo:** Grupo 4

---

## 1. Compromiso con la Seguridad Humana

Tratándose de software diseñado para salvaguardar la integridad de defensores de derechos humanos y bienes comunales en la Región Mixteca de Oaxaca, la seguridad no es una característica opcional; es un imperativo ético de vida o muerte.

---

## 2. Reporte Responsable y Confidencial de Vulnerabilidades

Si detecta una falla de seguridad, riesgo de fuga de datos personales (PII) o vulnerabilidad criptográfica en el sistema, **NO abra un issue público en GitHub**.

Siga el siguiente protocolo:
1. Redacte un correo electrónico detallando la falla, el vector de ataque y los pasos de reproducción a:
   * **Contacto de Seguridad del Grupo 4:** `seguridad.grupo4.tlaxiaco@gmail.com`
2. Si la información involucra expedientes reales de comunidades agrarias, cifre su mensaje utilizando la llave PGP pública del equipo.
3. El equipo acusará recibo en un plazo máximo de **48 horas hábiles** y emitirá un parche o mitigación preliminar antes de cualquier divulgación coordinada.

---

## 3. Prácticas Criptográficas Obligatorias en el Código

* **Cifrado en Reposo:** Empleo exclusivo de **SQLCipher con AES-256** para bases de datos SQLite locales.
* **Firmas Digitales:** Algoritmos estándar basados en curvas elípticas seguras (**ed25519** para identidades W3C DID y **secp256k1** para transacciones en red).
* **Purga de Metadatos:** Filtro local previo obligatorio para eliminar datos EXIF, software creador, fecha de digitalización y marcas de agua antes de calcular cualquier hash o CID.
