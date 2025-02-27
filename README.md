# Backend para el Clon de Airbnb con Django y NextjS

El Backend para este proyecto se realiza con el framework de Python Django. 

Esta es la configuración inicial para que el proyecto quede implementado en contenedores de Docker.
En el que se tendrá el servidor para el proyecto y la conexión para la base de datos de Postgresql

Para hacer funcionar el proyecto se requiere tener instalado Docker Desktop

## Descarga de Repositorio (desde gitbash)

```
git clone https://github.com/franlop24/djangobnb-backend djangobnb_backend

cd djangobnb_backend
```

### Construir la imagen de Docker
```
docker compose up --build
```

Con este comando construimos la imagen de docker con los servicios ya configurados, en este paso la terminal se muestra como si hubiéramos ejecutado ```python manage.py runserver```

Detenemos con ```Ctrl + C```

### Levantar el contenedor en segundo plano

```
docker compose up -d
```

Para probar verificamos que en el navegador podamos ver el proyecto accedemos a ```localhost:8000```

### Comandos manage.py

Los comandos con los que hemos trabajado con django funcionaran de la misma manera, solo que para que se ejecuten dentro del contenedor será de la siguiente forma

```
docker compose exec web python manage.py createsuperuser
docker compose exec web python manage.py startapp  
docker compose exec web python manage.py migrate app
docker compose exec web python manage.py makemigrations
```