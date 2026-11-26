# Objetivo 4: Manejo Inseguro de Errores (Stack Traces)

La diferencia principal entre un mensaje de error genérico y un Stack Trace expuesto en producción está en cuánta información interna revela al usuario frente a una falla:

El Mensaje de error genérico muestra un aviso simple, amigable y sin detalles técnicos internos, por ejemplo, "Ocurrió un error inesperado, intentá de nuevo más tarde" o una página 500 Internal Server Error personalizada, a veces acompañada de un identificador de correlación (error_id) para rastrearlo en los logs internos. No expone rutas, código, consultas ni versiones mientras que el Stack Trace es el registro detallado de la secuencia de llamadas a funciones o métodos que estaban activas en memoria cuando ocurrió una excepción no controlada. Suele incluir el tipo de error, el mensaje técnico, los nombres de archivos, números de línea, rutas del sistema de archivos, variables o fragmentos de código y, en algunos frameworks en modo debug, hasta datos de entorno o parámetros de la petición.


## ¿Por qué revelar un Stack Trace detallado facilita enormemente la fase de explotación de un atacante?

Un Stack Trace detallado acelera la explotación porque convierte una falla ciega (caja negra) en un diagnóstico con coordenadas exactas. En lugar de adivinar cómo funciona la aplicación por ensayo y error, el atacante obtiene información técnica que reduce drásticamente el tiempo y el esfuerzo necesarios para construir un exploit funcional.
