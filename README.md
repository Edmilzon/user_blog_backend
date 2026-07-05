# Proyecto Spring Boot

API REST construida con Spring Boot 3.2.2 y Java 17, usando JPA/Hibernate con PostgreSQL.

## Requisitos

- **Java 17** (JDK)
- **PostgreSQL** corriendo en `localhost:5432`

## Configuración

1. Crea la base de datos en PostgreSQL:

```sql
CREATE DATABASE Proyecto1;
```

2. Las credenciales se configuran en `src/main/resources/application.yaml`:

```yaml
server:
  port: 9090

spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/Proyecto1
    username: postgres
    password: tu_contraseña
  jpa:
    show-sql: true
    hibernate:
      ddl-auto: update
```

> El servidor corre en el puerto **9090**, no en el 8080 por defecto.

## Ejecución

```bash
./mvnw spring-boot:run
```

El servidor inicia en `http://localhost:9090`.

## Pruebas

```bash
./mvnw test
```

Requiere una instancia de PostgreSQL accesible.

## Endpoints

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET    | `/user` | Listar usuarios |
| GET    | `/user/{id}` | Obtener usuario por ID |
| POST   | `/user` | Crear usuario |
| PUT    | `/user/{id}` | Actualizar usuario |
| DELETE | `/user/{id}` | Eliminar usuario |
| GET    | `/role` | Listar roles |
| GET    | `/role/{id}` | Obtener rol por ID |
| POST   | `/role` | Crear rol |
| PUT    | `/role/{id}` | Actualizar rol |
| DELETE | `/role/{id}` | Eliminar rol |
| GET    | `/blog` | Listar blogs |
| GET    | `/blog/{id}` | Obtener blog por ID |
| POST   | `/blog` | Crear blog |
| PUT    | `/blog/{id}` | Actualizar blog |
| DELETE | `/blog/{id}` | Eliminar blog |
| GET    | `/article` | Listar artículos |
| GET    | `/article/{id}` | Obtener artículo por ID |
| POST   | `/article` | Crear artículo |
| PUT    | `/article/{id}` | Actualizar artículo |
| DELETE | `/article/{id}` | Eliminar artículo |

## Estructura del proyecto

```
src/main/java/com/infsis/Proyecto/Spring/Boot/
├── ProyectoSpringBootApplication.java   ← Punto de entrada
├── Models/                              ← Entidades JPA (User, Role, Blog, Article)
├── DTOs/                                ← Objetos de transferencia de datos
├── controllers/                         ← Controladores REST
└── services/
    ├── interfaces/                      ← Contratos de servicio
    └── implement/                       ← Implementaciones (@Service)
```

## Tecnologías

- **Spring Boot** 3.2.2
- **Spring Data JPA** + **Hibernate**
- **Spring Web** (REST)
- **PostgreSQL**
- **Maven** (wrapper incluido)
- **Java 17**
