# [ID-HALLAZGO] - [Título Descriptivo de la Vulnerabilidad]

| Campo | Detalle |
| :--- | :--- |
| **Proyecto / Aplicación** | `[Nombre de la aplicación o sistema evaluado]` |
| **Fecha de Detección** | `[AAAA-MM-DD]` |
| **Auditor / Pentester** | `[Tu Nombre / Alias]` |
| **Estado** | `[Abierto / En Remediación / Mitigado]` |
| **Severidad Global** | `[Crítica / Alta / Media / Baja / Informativa]` |
| **Puntuación CVSS** | `[Ej. 8.6 (High)]` |

---

## 1. Resumen Ejecutivo
* **¿Qué se encontró?**
  
* **Impacto en el Negocio:**
  
* **Prioridad de Atención:**
  Ej.: Inmediata (24-48 horas) / Corto plazo (7 días).]

---

## 2. Detalles Técnicos
* **Activo / Endpoint Afectado:** `[URL, IP, puerto, ruta de API o archivo]`
* **Parámetro / Componente Vulnerable:** `[Ej. Parámetro GET 'id', cabecera HTTP, token JWT]`
* **Clasificación Estándar:**
  * **OWASP Top 10:** `[Ej. A01:2021 - Broken Access Control]`
  * **CWE:** `[Ej. CWE-639: Authorization Bypass Through User-Controlled Key]`
* **Análisis de Causa Raíz:**
  [Explicación técnica profunda.]

---


## 3. Métricas CVSS (v3.1 / v4.0)
* **Puntuación Base:** `[0.0 - 10.0]` (`[Severidad]`)
* **Vector CVSS:** `CVSS:3.1/AV:[N|A|L|P]/AC:[L|H]/PR:[N|L|H]/UI:[N|R]/S:[U|C]/C:[N|L|H]/I:[N|L|H]/A:[N|L|H]`

| Métrica | Valor Seleccionado | Justificación |
| :--- | :--- | :--- |
| **Vector de Ataque (AV)** | `[Ej. Red (N)]` | `[Ej. Explotable de forma remota a través de Internet.]` |
| **Complejidad del Ataque (AC)** | `[Ej. Baja (L)]` | `[Ej. No requiere condiciones especiales ni race conditions.]` |
| **Privilegios Requeridos (PR)** | `[Ej. Bajos (L)]` | `[Ej. Basta con una cuenta de usuario estándar.]` |
| **Interacción del Usuario (UI)** | `[Ej. Ninguna (N)]` | `[Ej. El atacante ejecuta la acción directamente sin engañar a una víctima.]` |
| **Alcance (S)** | `[Ej. Sin cambios (U)]` | `[Ej. El impacto se limita al componente vulnerable.]` |
| **Confidencialidad (C)** | `[Ej. Alta (H)]` | `[Ej. Acceso total a registros sensibles de otros usuarios.]` |
| **Integridad (I)** | `[Ej. Ninguna (N)]` | `[Ej. Solo lectura de información.]` |
| **Disponibilidad (A)** | `[Ej. Ninguna (N)]` | `[Ej. No afecta la continuidad del servicio.]` |


---

## 4. Prueba de Concepto (PoC)
* **Prerrequisitos:**
  1. `[Ej. Contar con dos cuentas de prueba: Usuario A (ID: 101) y Usuario B (ID: 102).]`
  2. `[Ej. Herramienta proxy HTTP (Burp Suite / Caido) o cliente cURL.]`

* **Pasos para Reproducir:**
  1. Iniciar sesión en la aplicación con las credenciales del **Usuario A** y capturar su token de sesión.
  2. Navegar hacia la sección `[Nombre de la sección]` y observar la petición HTTP generada hacia `[Endpoint]`.
  3. Interceptar la solicitud y modificar el parámetro `[nombre_parametro]` cambiando el valor `101` por `102` (perteneciente al **Usuario B**).
  4. Reenviar la petición modificada y observar que el servidor responde con código `200 OK` devolviendo la información privada del **Usuario B**.

* **Evidencia Técnica (Petición y Respuesta):**
  ```http
  GET /api/v1/facturas/102 HTTP/1.1
  Host: ejemplo.com
  Authorization: Bearer <TOKEN_USUARIO_A>

## 5. Recomendaciones de Remediación

* **Solución Principal (Corto / Mediano Plazo):**
[Descripción clara de los cambios a nivel de código o arquitectura necesarios para erradicar la vulnerabilidad.]


---------------------------------------------------------------------------------------------------------------------------------------------------------------------


### 1. ¿Por qué está organizada así la plantilla?

Un reporte o ticket de seguridad profesional debe responder a audiencias muy diferentes dentro de una misma organización, ordenando la información de lo estratégico a lo operativo:

1. **Encabezado / Metadatos:** Permite triaje rápido, trazabilidad en sistemas de gestión (Jira, DefectDojo, GitHub Issues) y filtrado por criticidad o activo afectado.
2. **Resumen Ejecutivo:** Traduce un problema técnico a **riesgo de negocio**. Está diseñado para perfiles gerenciales (CISO, CTO, Product Owners, Directivos) que necesitan decidir presupuestos, prioridades y tiempos de salida a producción sin leer código.
3. **Métricas CVSS:** Proporciona un **estándar objetivo e internacional** para medir la severidad. Evita discusiones subjetivas sobre si un fallo es "grave" o "leve", justificando cada vector (acceso, privilegios, impacto en tríada CIA).
4. **Detalles Técnicos:** Conecta el hallazgo con taxonomías reconocidas (**OWASP, CWE**) y explica la **causa raíz**, permitiendo que arquitectos y líderes técnicos entiendan si es un error puntual o un fallo sistémico repetido en otros módulos.
5. **Prueba de Concepto (PoC) paso a paso:** Demuestra de manera **irrefutable y reproducible** que la vulnerabilidad existe y es explotable. Incluye petición/respuesta HTTP y capturas con datos sensibles debidamente censurados.
6. **Recomendaciones de Remediación:** Transforma el reporte de una simple lista de críticas en una **guía práctica de solución**, ofreciendo ejemplos de código seguro y criterios claros de *retest*.

---

### 2. ¿Qué valor genera al usuario final que lee un ticket con esta plantilla?

* **Para el Desarrollador (Equipo de Ingeniería):**
  * **Ahorro de tiempo en diagnóstico:** No tiene que adivinar dónde ni por qué falla la aplicación; cuenta con el *endpoint*, el parámetro exacto, los pasos deterministas para reproducirlo localmente y un ejemplo concreto de cómo corregirlo.
  * **Validación autónoma:** Gracias al criterio de *retest*, puede comprobar por sí mismo que su parche cierra la brecha antes de devolver el ticket a seguridad.
* **Para el Líder Técnico / Arquitecto de Software:**
  * **Visión sistémica:** Al identificar la causa raíz y la clasificación CWE/OWASP, puede auditar si el mismo patrón inseguro se repite en otros servicios o microservicios del proyecto.
* **Para Directivos y Gestión de Riesgos:**
  * **Toma de decisiones informada:** El Resumen Ejecutivo y la puntuación CVSS permiten priorizar recursos de ingeniería sobre las vulnerabilidades que realmente comprometen la continuidad operativa, los datos de clientes o el cumplimiento legal.
* **Para la Relación entre Seguridad y Desarrollo:**
  * **Elimina fricciones y falsos positivos:** La evidencia objetiva de la PoC evita debates sobre la validez del hallazgo y fomenta una cultura colaborativa orientada a construir software más seguro.

