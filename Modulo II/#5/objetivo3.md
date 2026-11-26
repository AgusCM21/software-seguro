# Objetivo 3: Peligros del "Listado de Directorio"

1. Cuando un cliente (como un navegador o una herramienta automatizada) solicita una ruta que apunta a un directorio, el servidor web revisa primero si existe un archivo de índice configurado por defecto (index.html, index.php, etc.). Si no encuentra ese archivo de índice y el listado de directorios está habilitado:

-Resolución de ruta y permisos: El servidor comprueba que la carpeta exista en el sistema de archivos y que el usuario del proceso del servidor web (por ejemplo, www-data o apache) tenga permiso de lectura (r) y ejecución (x) sobre ese directorio.

-Lectura del directorio: En lugar de devolver un error 403 Forbidden o 404 Not Found, el módulo encargado del listado lee las entradas del directorio en el sistema de archivos.

-Generación dinámica del índice: El servidor construye al vuelo una respuesta HTTP 200 OK (generalmente con Content-Type: text/html; charset=utf-8 o formato JSON/XML según la configuración) conteniendo un listado estructurado con los nombres de archivos, subcarpetas, fechas de última modificación y tamaños.

-Exposición y enumeración: Cualquier visitante o un crawler o scanner como dirsearch, ffuf o gobuster puede hacer clic en los enlaces o recorrer recursivamente las subcarpetas para mapear la estructura interna del proyecto sin necesidad de adivinar nombres de archivos.


2. Cuando el listado está activo en carpetas públicas o mal segmentadas, suelen filtrarse archivos que nunca debieron quedar en la raíz o en rutas accesibles vía HTTP:

-Respaldos y volcados: Archivos .zip, .tar.gz, .sql, .bak o copias de seguridad de bases de datos y del código fuente.

-Configuración y credenciales: Archivos .env, config.php, wp-config.php, settings.py, credentials.json o configuraciones de despliegue con claves de API, contraseñas de base de datos o tokens secretos.

-Control de versiones y dependencias: Carpetas como .git/ (que permiten reconstruir historial y código fuente), .svn/, composer.json / package.json o archivos de lock que revelan versiones exactas de librerías y ayudan a buscar vulnerabilidades conocidas.

-Registros (logs) y depuración: Archivos .log, volcados de error o scripts de prueba (phpinfo.php, test.php) que exponen rutas internas del servidor, versiones de software, consultas o trazas de ejecución.

-Documentación y activos internos: Manuales internos, diagramas de arquitectura, exportaciones de usuarios o archivos subidos por clientes sin control de autorización.

## ¿Cómo mitigarlo?

La mitigación combina desactivar explícitamente el listado en el servidor web y mantener una buena higiene de archivos en el directorio público.
