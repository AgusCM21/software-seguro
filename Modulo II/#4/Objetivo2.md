# Objetivo 2: Análisis de la Triada CIA

## 1. Confidencialidad

La confidencialidad hace referencia al proceso de asegurarse de que sólo puedan acceder a la información aquellos que estén autorizados. Se trata sobre seguridad a la privacidad.

## 2. Integridad

La integridad se refiere a que la información no se vea alterada, que sea siempre consistente, precisa, confiable y no se vea comprometida.

## 3. Disponibilidad

Garantizar que los sistemas, aplicaciones y datos sean fácilmente accesibles para los usuarios autorizados siempre que se necesiten.

## Ejemplos de vulnerabilidades

### A. Compromiso de la Confidencialidad
**IDOR (Insecure Direct Object Reference)**.
Ocurre cuando una aplicación web permite a un usuario modificar un parámetro (por ejemplo, cambiar el ID en una URL como `/api/user/104` por `/api/user/105`) sin validar correctamente si tiene permisos para ver esa información. Esto permite acceder a datos privados de otros usuarios.

### B. Compromiso de la Integridad
**SQL Injection (Inyección SQL)** o **Manipulación de Parámetros en Transacciones**.

Si una aplicación no sanea adecuadamente las entradas del usuario, un atacante puede inyectar sentencias SQL maliciosas para alterar registros directamente en la base de datos (por ejemplo, modificando el saldo de su cuenta bancaria o alterando el estado de un pedido). Esto vulnera la veracidad y exactitud de los datos.

### C. Compromiso de la Disponibilidad*
**Ataque de Denegación de Servicio (DoS / DDoS)** o **Agotamiento de Recursos por Peticiones Pesadas**.
Un atacante satura un servidor web con miles de peticiones falsas por segundo o explota una consulta ineficiente de base de datos que consume toda la memoria y CPU. Como consecuencia, el sitio web deja de responder o se cae por completo, impidiendo el acceso a los usuarios legítimos.
