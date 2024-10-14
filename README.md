# PRACTICA1.2




Escribimos la línea de comando asociada 



     ``docker create --name asir_web1 -p 8000:80 -v  "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd ``





### CREAR OTRO CONTENEDOR 'ASIR_WEB2' CON EL MISMO DIRECTORIO PERO CON OTRO PUERTO 8090




Empleamos de nuevo la misma estructura de línea de comandos anteriormente utilizada



     ``docker create --name asir_web2 -p 8090:80 -v  "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd ``





### COMPROBAR QUE LOS DOS SERVICIOS MUESTRAN LA MISMA PÁGINA 




Inicializamos los contenedores .



      ``docker start asir_web1``
      
      
      ``docker start asir_web2 ``   



Para comprobarlo se introduce en la barra de URL respectivamente  las expresiones.

localhost:8090

localhost:8000 
