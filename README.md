## PRÁCTICA 2



*******




### COMPROBAR QUE TIENES UNA IMAGEN HTTPD


Se usa el comando de docker ya empleado con anterioridad

   ``docker images``


Si no se tiene la imagen , habrá que descargarla 


   ``docker pull httpd``
   





### CREAR UN CONTENEDOR DE NOMBRE 'ASIR_HTTPD'



   ``docker create --name asir_httpd -p 8080:80 -v  "$PWD"/htdocs:/usr/local/apache2/htdocs/httpd ``






### MAPEA EL PUERTO 80 DEL CONTENEDOR CON 8080 DE TU MÁQUINA 



Se emplea el comando _bind mount_ para que el directorio httdocs  se monte en un directorio determinado que tu definas






### MOSTRAR UNA PÁGINA HTML ALOJADA EN APACHE2 DESDE TU NAVEGADOR 



En primera instancia iniciamos el contenedor 


    ``docker start asir_httpd``


Posteriormente , se introduce en la barra de URL asociada a tu navegador la expresión  


localhost:8080





### CREAR UN CONTENEDOR 'ASIR_WEB1' QUE USE UN MISMO DIRECTORIO PARA 'HTDOCS Y EL PUERTO 8000




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


