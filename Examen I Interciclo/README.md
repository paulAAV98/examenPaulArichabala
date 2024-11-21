# Docker Angular + Apache

## Descripción
Esta imagen utiliza Debian como base para servir una aplicación Angular a través de Apache. 

## Requisitos
- Docker
- Angular CLI

## Instrucciones
1. Clonar este repositorio:
   ```bash
   git clone <repositorio>
   cd <repositorio>
2.	Construir la imagen Docker:
bash
Copiar código
docker build -t angular-apache .
3.	Correr el contenedor:
bash
Copiar código
docker run -d -p 80:80 angular-apache
