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
docker ps
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
Crear una Base de Datos y una tabla
```psql
create database prueba
\c prueba
create table teclados (
id serial primary key,
nombre varchar(20)
);
\dt
```

## Configuración por entorno

```
MESSAGE_APP1=<Colocar nombre ...>
MESSAGE_APP2=<Colocar nombre ...>
MESSAGE_APP3=>Colocar nombre ...>
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

## Volúmenes anónimos
Son volúmenes temporales generados por la imagen, además si este no recibe un nombre y se elimina el contenedor, este almacenamiento también se borrará.
## Volúmenes nombrados
Son volúmenes separados de los contenedores, por lo que permiten persistir datos de base de datos o producción, y compartir su contenido entre otros contenedores. En el desarrollo de este laboratorio se implemento este tipo de volumen para poder persistir el contenido de la Base de Datos.

# Créditos

- Reyes Pinillos, Fabrizio Juan 

# Capturas
Primer Commit

<img width="738" height="231" alt="Captura de pantalla 2026-09-12 130412" src="https://github.com/user-attachments/assets/c50d6a87-e002-4f27-b091-d09ec880306d" />

Probando la imagen

<img width="708" height="258" alt="Captura de pantalla 2026-09-12 132048" src="https://github.com/user-attachments/assets/add07007-9c88-4ba0-8c28-c03edbbeffbd" />

Primera copia de la API devolviendo mi nombre

<img width="555" height="157" alt="Captura de pantalla 2026-09-12 140752" src="https://github.com/user-attachments/assets/072a49a4-3a63-43ce-9c29-cc7c0a6783f8" />

Usando .env para que la copia de la API devuelva mi nombre

<img width="568" height="164" alt="Captura de pantalla 2026-09-12 142612" src="https://github.com/user-attachments/assets/2bf70e4b-bf5a-4fb3-bc2e-e7573cef3913" />

Las 3 copias de la API

<img width="1407" height="534" alt="Captura de pantalla 2026-09-12 144214" src="https://github.com/user-attachments/assets/2896167d-9c2e-43e1-9769-85a344c37c50" />

<img width="582" height="433" alt="Captura de pantalla 2026-09-12 144243" src="https://github.com/user-attachments/assets/a7db13e3-4952-4098-b9d4-2dbe9d20cd9f" />

Actualización de los mensajes de cada copia de la API

<img width="572" height="439" alt="Captura de pantalla 2026-09-12 224057" src="https://github.com/user-attachments/assets/6e5ab579-0451-48a9-a082-495fcec37521" />

Configuración de Postgresql

<img width="1281" height="553" alt="Captura de pantalla 2026-09-12 162603" src="https://github.com/user-attachments/assets/473f6a23-8e8b-46e9-a360-c761edc344f9" />

<img width="992" height="137" alt="Captura de pantalla 2026-09-12 162853" src="https://github.com/user-attachments/assets/5a5ae0ae-fa68-433f-aec2-caf1d959757b" />

Creación de una base de datos para probar el volumen

<img width="458" height="293" alt="Captura de pantalla 2026-09-12 172909" src="https://github.com/user-attachments/assets/07820033-c5e9-45ea-8159-9eb44c0a21ac" />
