# Apagar la IA

1. Desencriptar el hash md5 de las URL, obtener ambos valores.
2. Realizar un intruder con un rango más grande en los que se encuentren ambos valores obtenidos de la desencriptación para poder obtener todos aquellos que puedan tener códigos de 16 digitos.
3. En el intruder ingresamos una lista de hashes y realizamos el ataque para verificar cuáles son válidos.
4. Al obtener los hashes, hacemos un grep y volvemos a ejecutar el intruder para que nos devuelva el código de 16 dígitos.
5. Pasar el código a hash md5.


# El mejor secreto

Para poder resolver este laboratorio realicé los siguientes pasos:
1. Ver el video detenidamente y analizar qué botones eran seleccionados y cuántas veces se repetían.
2. Armar una secuencia con los dígitos analizados, en este caso ABCCDADDDDEC.
3. Mediante un script realizar fuerza bruta cambiando cada valor que corresponde en la secuencia para ver cuál abre el archivo. 

# Votación

1. Realizar un voto e interceptar la petición.
2. Al verificar que se setea un cookie de voto, podemos realizar votos mientras no tenga cookie. Realizamos un intruder seleccionando la variable que pueda cambiarse como alguna versión y generamos un ataque con la cantidad que queramos de votos.
   
# Votación nueva versión
1. Interceptar la petición de voto.
2. Agregar una cabecera que tenga una ip para poder cambiarla como "X-Forwarded-For".
3. Hacer un intruder usando la ip para cambiarla y realizar varias peticiones.
