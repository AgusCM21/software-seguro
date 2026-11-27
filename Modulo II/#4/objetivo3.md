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

* ** Solución Principal (Corto / Mediano Plazo): **
[Descripción clara de los cambios a nivel de código o arquitectura necesarios para erradicar la vulnerabilidad.]
