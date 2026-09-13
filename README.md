# Laboratorio 02

Hoy utilizaremos docker compose para poder desplegar su trabajo. Servicio web y una base de datos

## Stack
API
  - Minimal API
    - Debe retornar un mensaje incluyendo mi nombre
  - Docker
- docker run -d --rm -p 3000:3000 nmatsui/hello-world-api. 
  - API-1: 
    -  Nombre: app1      puerto:3000:3000
  - API-2:
    - Nombre: app2      puerto:3001:3000
  - API-3: 
    - Nombre: app3      puerto:3002:3000

BD
  - PostgreSQL
- docker run --name=db -e POSTGRES_PASSWORD=secret -d -v postgres_data:/var/lib/postgresql postgres


# Indicaciones

## Comandos

```bash
docker compose up -d
```

## Configuración por entorno

```
MESSAGE=<Colocar nombre>
POSTGRES_USAR=<Colocar nombre de usuario>
POSTGRES_PASSWORD=<Colocar contraseña>
```
# Tipos de Redes / Controladores de Red

## bridge
Tipo de red predeterminada, sirve para comunicar a los contenedores entre sí, mediante una red interna en el host.
## host
Elimina el aislamiento de red entre los contenedores y la red del equipo.
## overlay
Conecta multiples servicios entre sí, incluso si se encuentran en diferentes nodos o maquinas.
## ipvlan
Permite un control total sobre las direcciones IPv4  y IPv6
## macvlan
Permiten asignar una dirección MAC a cada contenedor, pareciendo como un dispositivo más para la red y permitiendole obtener su propia dirección IP.
## none
Aisla por completo a un contenedor perdiendo su conección con la red.
# Tipos de Volumenes



# Creditos

- Reyes Pinillos, Fabrizio

# ETC
