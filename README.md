# Laboratorio 02


Hoy utilizaremos Docker Compose para poder desplegar nuestro trabajo.

Se implementará un servicio web (API) y una base de datos utilizando contenedores Docker.


# Stack


## API

- Minimal API
- Node.js
- Express
- Docker


La API debe retornar un mensaje incluyendo el nombre del estudiante utilizando variables de entorno.


Se desplegaron 3 copias de la API mediante Docker Compose:

- api1
- api2
- api3


Cada instancia utiliza la misma imagen construida localmente mediante un Dockerfile.


## BD

- PostgreSQL


La base de datos PostgreSQL es desplegada mediante Docker Compose y utiliza variables de entorno para su configuración.


# Indicaciones


## Comandos


Para construir las imágenes y desplegar los servicios:


```bash
docker compose up -d --build
```


Para verificar los servicios ejecutándose:


```bash
docker ps
```


Para detener los servicios:


```bash
docker compose down
```


# Configuración por entorno


Las variables de entorno utilizadas por el proyecto son:


```env
MESSAGE=<Colocar nombre>

POSTGRES_USER=<Usuario BD>

POSTGRES_PASSWORD=<Password BD>

POSTGRES_DB=<Nombre BD>
```


Ejemplo utilizado:


```env
MESSAGE=Franco

POSTGRES_USER=admin

POSTGRES_PASSWORD=123456

POSTGRES_DB=laboratorio
```


# Volúmenes


El proyecto utiliza un volumen Docker para mantener la información de PostgreSQL aunque el contenedor sea eliminado.


Volumen utilizado:


```
postgres_data
```


# Tipos de redes Docker


## Bridge

Es la red utilizada normalmente por Docker Compose.

Permite la comunicación entre contenedores mediante una red privada administrada por Docker.


## Host

El contenedor utiliza directamente la red del equipo anfitrión.


## None

El contenedor queda aislado sin comunicación de red.



# Tipos de volúmenes Docker


## Docker Volume

Volumen administrado por Docker.

Permite almacenar información fuera del ciclo de vida del contenedor.


## Bind Mount

Permite enlazar una carpeta del sistema local con una carpeta dentro del contenedor.


## Tmpfs

Almacenamiento temporal utilizando memoria RAM.

Los datos desaparecen cuando el contenedor se detiene.



# Créditos


- Franco Mori Galarza


# Referencias


Docker Hub PostgreSQL:

https://hub.docker.com/_/postgres


Docker Hub Hello World API:

https://hub.docker.com/r/nmatsui/hello-world-api


Conventional Commits:

https://www.conventionalcommits.org/en/v1.0.0/

# Capturas



 