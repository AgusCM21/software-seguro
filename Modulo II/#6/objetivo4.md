# Objetivo 4: Análisis del Ataque de Algoritmo "Ninguno"

## Una de las vulnerabilidades más críticas en la implementación de JWT es aceptar el algoritmo Ninguno. Investiga y explica técnicamente por qué un backend vulnerable a esto permite a un atacante falsificar cualquier identidad sin necesidad de conocer la clave secreta del servidor.

## ¿por qué un backend vulnerable a esto permite a un atacante falsificar cualquier identidad sin necesidad de conocer la clave secreta del servidor?
Debido a que la clave secreta solo es necesaria para generar o verificar una firma criptográfica, y cuando el backend acepta "alg": "none", anula ese paso de verificación por completo.

Al ocurrir esto se rompe el vínculo entre lo que dice el token y lo que el servidor puede comprobar:

-Sin firma no hay prueba de integridad: En un JWT válido, la firma garantiza que nadie alteró el payload después de ser emitido. Si el algoritmo es "none", el servidor no exige firma válida y trata un token sin firmar (o con firma vacía) como si fuera auténtico.

-El cliente controla el algoritmo que el servidor va a usar: Un backend vulnerable lee "alg" desde el header que envía el propio atacante. En lugar de imponer su propio algoritmo esperado (como HS256 o RS256), deja que el atacante elija cómo se va a "verificar" su propio token.

-El payload se acepta sin cuestionar: Como el token no es rechazado por falta de firma, el servidor decodifica el payload en Base64URL y toma los datos de identidad (sub, user, email, role, admin) como ciertos.

-La clave secreta queda fuera de la ecuación: La clave secreta del servidor se usa para calcular o comprobar el HMAC de la firma. Si no se calcula ni se verifica ninguna firma porque "alg" es "none", la clave nunca se consulta ni hace falta conocerla para que el token pase la validación.
