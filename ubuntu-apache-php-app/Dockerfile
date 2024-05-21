# Usar una imagen base de Ubuntu
FROM ubuntu:20.04

# Configurar la variable de entorno para desactivar la interacción durante la instalación de paquetes
ENV DEBIAN_FRONTEND=noninteractive

# Establecer la zona horaria para evitar la interacción durante la instalación de paquetes relacionados con el tiempo
ENV TZ=America/New_York

# Actualizar la lista de paquetes e instalar Apache y PHP
RUN apt-get update && \
    apt-get install -y apache2 php libapache2-mod-php tzdata

# Descargar la aplicación web PHP y copiarla al directorio de Apache
RUN mkdir -p /var/www/html && \
    echo "<?php phpinfo(); ?>" > /var/www/html/index.php

# Exponer el puerto 80
EXPOSE 80

# Comando para iniciar Apache en el contenedor
CMD ["apachectl", "-D", "FOREGROUND"]
