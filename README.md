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

Usados para construir y verificar los contenedores
```bash
docker compose up -d
docker compose ps
```

Usados para probar las API
```bash
curl http://localhost:3000
curl http://localhost:3001
curl http://localhost:3002
```

Usados para el repositorio
```bash
git add .
git commit -m "..."
git push otrigin main
```

Usado para ingresar a postgresql
```bash
docker compose exec db psql -U <Colocar nombre de usuario> -d postgres
```
Crear una Base de Datos
```psql
create database prueba
```


## Configuración por entorno

```
MESSAGE=<Colocar nombre>
POSTGRES_USER=<Colocar nombre de usuario>
POSTGRES_PASSWORD=<Colocar contraseña>
```
# Tipos de Redes / Controladores de Red

## bridge
Tipo de red predeterminada, sirve para comunicar a los contenedores entre sí, mediante una red interna en el host.
## host
Elimina el aislamiento de red entre los contenedores y la red del equipo.
## overlay
Conecta múltiples servicios entre sí, incluso si se encuentran en diferentes nodos o maquinas.
## ipvlan
Permite un control total sobre las direcciones IPv4  y IPv6
## macvlan
Permiten asignar una dirección MAC a cada contenedor, pareciendo como un dispositivo más para la red y permitiéndole obtener su propia dirección IP.
## none
Aísla por completo a un contenedor perdiendo su conexión con la red.

# Tipos de Volúmenes

## Volumen anónimos
Son volúmenes temporales generados por la imagen, además si este no recibe un nombre y se elimina el contenedor, este almacenamiento también se borrará.
## Volúmen nombrados
Son volúmenes separados de los contenedores, por lo que permiten persistir datos de base de datos o producción, y compartir su contenido entre otros contenedores. En el desarrollo de este laboratorio se implemento este tipo de volumen para poder persistir el contenido de la Base de Datos.

# Créditos

- Reyes Pinillos, Fabrizio Juan 

# Capturas
Primer Commit

<img width="738" height="231" alt="Captura de pantalla 2026-09-12 130412" src="https://github.com/user-attachments/assets/c50d6a87-e002-4f27-b091-d09ec880306d" />

Probando la imagen

<img width="708" height="258" alt="Captura de pantalla 2026-09-12 132048" src="https://github.com/user-attachments/assets/add07007-9c88-4ba0-8c28-c03edbbeffbd" />

Primera copia de la API devolviendo mi nombre
<img width="564" height="177" alt="Captura de pantalla 2026-09-12 140124" src="https://github.com/user-attachments/assets/8690300a-1e38-41f6-8cbc-1fe86d6bdb9e" />
