*¿Qué es TLS Handshake?*

El TLS Handshake consiste en el proceso que ocurre antes de que el navegador envíe una primera petición HTTP a un sitio web seguro, con el objetivo de que el cliente y el servidor se identifiquen y acuerden qué algoritmos de cifrado y versión de protocolo se van a utilizar, es decir, cómo se van a comunicar de forma segura y luego generan una clave de sesión compartida para cifrar los datos que van a intercambiar.

*¿Cómo funciona?*

1. Client Hello
   El navegador inicia la conexión y envía información sobre las versiones de TLS y algoritmos de cifrado que soporta.

2. Server Hello
   El servidor responde seleccionando los algoritmos de seguridad que se utilizarán durante la conexión.

3. Envío del certificado digital
   El servidor envía su certificado digital para demostrar su identidad.

4. El navegador verifica que el certificado sea válido, pertenezca al sitio web correcto y haya sido emitido por una Autoridad de Certificación de confianza.

5. Generación de la clave de sesión compartida.
   El cliente y el servidor establecen un secreto compartido para cifrar la comunicación anterior.

6. Inicio de la comunicación segura.
   Finalizado el handshake, ambas partes comienzan a intercambiar datos mediante HTTPS utilizando la clave de sesión que ha sido    generada.

*¿Qué función cumplen los certificados digitales?*

Los certificados digitales sirven para que el servidor pueda demostrar su identidad al navegador, como una credencial electrónica que es emitida por una autoridad de certificación. Demuestra al navegador que está hablando con un servidor legítimo y no un atacante.

*¿Por qué se usan dos tipos de cifrados?*

El TLS utiliza cifrado simétrico y asimétrico debido a que tienen funciones diferentes. 
-El simétrico usa una única clave compartida entre cliente y servidor. Protege todos los datos. Es más rápido y eficiente para procesar grandes cantidades de información.
-El asimétrico utiliza una clave pública, una privada y se emplea durante el handshake para autenticar al servidor y establecer de forma segura una clave de sesión.
