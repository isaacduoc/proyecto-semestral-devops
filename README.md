# Proyecto Semestral DevOps

## Descripción
Proyecto semestral desarrollado utilizando arquitectura basada en contenedores Docker, integrando frontend, microservicios backend y base de datos MySQL mediante Docker Compose.

---

## Tecnologías Utilizadas

- Docker
- Docker Compose
- React + Vite
- Spring Boot
- MySQL
- GitHub

---

## Arquitectura del Proyecto

Frontend React -> Backend Despacho -> Backend Ventas -> MySQL

---

## Contenedores Docker

- frontend_container
- backend_despacho_container
- backend_ventas_container
- mysql_container

---

## Puertos Utilizados

| Servicio | Puerto |
|----------|---------|
| Frontend | 3000 |
| Backend Despacho | 8081 |
| Backend Ventas | 8082 |

---

## Ejecución del Proyecto

### Levantar contenedores

```bash
docker compose up --build -d
```

### Ver contenedores activos

```bash
docker ps
```

### Detener contenedores

```bash
docker compose down
```

---

## Docker

El proyecto utiliza:

- Dockerfiles personalizados
- Multi-stage builds
- Usuario no root
- Persistencia mediante volúmenes
- Redes Docker internas
- Contenedores desacoplados

---

## Autor

Isaac Arias