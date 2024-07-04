# Proyecto Laravel con Docker

Este proyecto implementa una aplicación Laravel utilizando Docker Compose con 4 servicios: Laravel, Nginx, MySQL y un servicio HTTP aleatorio.

## Requisitos previos

- Docker
- Docker Compose

## Configuración

1. Clona este repositorio:
git clone <url-del-repositorio>
cd <nombre-del-directorio>

2. Copia el archivo `.env.example` a `.env` y configura las variables de entorno, especialmente las de la base de datos.

3. Construye y levanta los contenedores:

docker-compose up -d --build

4. Instala las dependencias de Laravel:

docker-compose exec app composer install

5. Genera la clave de la aplicación:

docker-compose exec app php artisan key:generate

6. Ejecuta las migraciones y siembra la base de datos:

docker-compose exec app php artisan migrate --seed

## Uso

- Accede a la aplicación Laravel en `http://devops.test`
- Para iniciar el servicio HTTP aleatorio:

docker-compose --profile random up -d

Luego accede a `http://devops.test/thiio`

## Pruebas

Para ejecutar las pruebas:

docker-compose exec app php artisan test

## Solución de problemas

Si encuentras algún problema, revisa los logs de Docker:

docker-compose logs

Para logs más detallados de un servicio específico:

docker-compose logs <nombre-del-servicio>