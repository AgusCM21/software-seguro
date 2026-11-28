# Objetivo 3: Anatomía de una Condición de Carrera (Race Condition)

###  Investiga y explica con tus palabras cómo un atacante podría utilizar herramientas (como el Turbo Intruder de Burp Suite) para enviar 50 peticiones simultáneas y lograr canjear un código de descuento de un solo uso múltiples veces antes de que el servidor actualice la base de datos.

Para lograrlo, primero se intercepta la petición de canje del cupón y se envía a Turbo Intruder (en Burp Suite), configurándolo para enviar 50 peticiones de forma concurrente. Al llegar casi al mismo tiempo, varias solicitudes pueden consultar la base de datos y comprobar que el cupón aún no fue utilizado antes de que la primera termine de actualizar su estado a "canjeado" (una falla de tiempo conocida como TOCTOU / Race Condition). Como el servidor no bloquea ni sincroniza esa operación de forma atómica, distintas peticiones pasan la validación en paralelo y permiten aplicar el descuento de un solo uso múltiples veces.
