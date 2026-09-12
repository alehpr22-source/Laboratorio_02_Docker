# Laboratorio 02

Hoy utilizaremos docker compose para poder desplegar su trabajo. Servicio web y una base de datos

## Stack
API
  - Minimal API
    - Debe retornar un mensaje incluyendo mi nombre
  - Docker
- docker run -d --rm -p 3000:3000 nmatsui/hello-world-api. 
  API-1: 
    Nombre: app1      puerto:3000:3000
  API-2:
    Nombre: app2      puerto:3001:3000
  API-3: 
    Nombre: app3      puerto:3002:3000

BD
  - PostgreSQL
- $ docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres


# Indicaciones

## Comandos

```bash
docker compose up -d
```

## Configuración por entorno

```
MESSAGE=<Colocar nombre>
```


# Creditos
- Walter Ivan Leturia Rodriguez

# ETC
