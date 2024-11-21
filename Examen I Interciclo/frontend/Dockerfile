# Imagen base
FROM debian:bullseye

# Actualizamos e instalamos dependencias necesarias
RUN apt-get update && apt-get upgrade -y && apt-get install -y \
    apache2 \
    curl \
    gnupg \
    build-essential

# Instalamos Node.js (versión 18 LTS)
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs

# Instalamos Angular CLI
RUN npm install -g @angular/cli

# Copiamos el proyecto Angular al contenedor
COPY ./examenPaulArichabala /app

# Configuramos el directorio de trabajo
WORKDIR /app

# Instalamos dependencias del proyecto
RUN npm install

# Construimos la aplicación en modo producción
RUN ng build --configuration production

# Copiamos los archivos construidos al directorio de Apache
RUN cp -r /app/dist/examen-paul-arichabala/* /var/www/html/

# Exponemos el puerto 80 para Apache
EXPOSE 80

# Arrancamos Apache
CMD ["apachectl", "-D", "FOREGROUND"]