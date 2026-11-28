#  Objetivo 1: Auditoría de Cookies y Banderas de Seguridad

### Discord

<img width="1669" height="290" alt="Captura de pantalla 2026-11-27 230107" src="https://github.com/user-attachments/assets/809cc2b2-1ce4-475a-82df-6225866e9015" />

-Cookies críticas de seguridad e infraestructura bien protegidas, HttpOnly: true y Secure: true.

### Facebook 

<img width="1614" height="231" alt="Captura de pantalla 2026-11-27 225629" src="https://github.com/user-attachments/assets/e71b7441-b911-4045-9a96-3b322c07f242" />

-Todas las cookies tienen Secure: true (ninguna viaja por algún HTTP plano).

La cookie crítica de sesión (xs) tiene HttpOnly: true y Secure: true, mientras que las cookies con HttpOnly: false corresponden solo a metadatos de interfaz o identificación pública de cuenta que el frontend necesita consultar.

### Instagram

<img width="1614" height="273" alt="Captura de pantalla 2026-11-27 225321" src="https://github.com/user-attachments/assets/416710b0-5431-451e-adfa-dbb5b626a542" />

-Para Instagram tenemos HttpOnly: true, Secure: true y SameSite: None. Estos tres campos están bien implementados para garantizar la seguridad del usuario.

# Bandera HttpOnly

## ¿Qué protege esta bandera?

La bandera HttpOnly para cookies garantiza que solo se pueda acceder a una cookie mediante HTTP e impide que JavaScript las lea. Esta función sirve como protección contra ataques XSS (Cross-Site Scripting) al impedir la lectura de cookies mediante JavaScript.

## ¿Qué riesgo corre el usuario si la cookie de sesión no tiene la bandera Secure activada?

La bandera Secure se utiliza para indicar que la cookie solo se puede transmitir mediante una conexión segura (SSL/HTTPS). Si se establece esta bandera, el navegador nunca enviará la cookie si la conexión es HTTP. Si la cookie de sesión no tiene la bandera Secure activada, el navegador permitirá que dicha cookie sea enviada a través de conexiones HTTP sin cifrar (en texto plano), exponiendo al usuario a riesgos críticos como el robo de cookies mediante ataques de intermediario (man-in-the-middle), secuestro de sesión (Session Hijacking), Intercepción en red (Sniffing).
