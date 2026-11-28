#  Objetivo 2: Ingeniería Inversa a JSON Web Tokens (JWT)

### JWT de Notas Universitarias.

access_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNzk1OTI1NjU4LCJpYXQiOjE3OTU4MzkyNTgsImp0aSI6Ijg4MTAyYzA2MjdkMjRmOGRiOGY5MzRlNzQ4ZjFhOTFmIiwidXNlcl9pZCI6IjI2In0.rMijznxLhLOCNGwQhUHEuNAMdhh5AhGqqO-lbEa0ick; expires=Sat, 28 Nov 2026 04:19:18

{
  "alg": "HS256",
  "typ": "JWT"
}

{
  "token_type": "access",
  "exp": 1795925658,
  "iat": 1795839258,
  "jti": "88102c0627d24f8db8f934e748f1a91f",
  "user_id": "26"
}

-Algoritmo de firma: HS256 (HMAC con SHA-256). Es un algoritmo de firma simétrica: el servidor firma y verifica el token usando una misma clave secreta compartida.

-No se envían roles ni permisos en el Payload. Dado que el Payload está codificado en Base64URL y no cifrado, cualquier persona que acceda al token puede leer su contenido sin conocer la clave secreta. En este caso no se exponen contraseñas, correos ni datos personales sensibles directos, pero sí se incluye el identificador de usuario junto con metadatos de control del token
