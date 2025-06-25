# Deployment-BackEnd

Este repositorio está preparado para el **despliegue del back-end** de [WHS Representaciones](https://github.com/DominidM/whsRepresentaciones).

---

## 📦 Descripción

Contiene el **Back-End** de WHS Representaciones desarrollado en **Java Spring Boot** con **Thymeleaf** y conexión a **PostgreSQL**.

---

## 🚀 Despliegue rápido en Azure o servidores compatibles

### 1. Requisitos

- Java 17 o superior
- Maven
- Base de datos PostgreSQL accesible
- Configuración de variables de entorno (o edición de `application.properties`)

---

### 2. Configuración

#### Variables necesarias (puedes usar variables de entorno o editar `src/main/resources/application.properties`):

```properties
# PostgreSQL connection
spring.datasource.url=jdbc:postgresql://<HOST>:<PORT>/<DB_NAME>
spring.datasource.username=<DB_USER>
spring.datasource.password=<DB_PASSWORD>

# JPA/Hibernate
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# (Opcional) Puerto de la app
server.port=8080
```

---

### 3. Compilación y ejecución local

```sh
# Compila el proyecto (genera el .jar)
mvn clean package

# Ejecuta el backend
java -jar target/*.jar
```

---

### 4. Despliegue en Azure App Service (Linux)

1. Sube el `.jar` generado en `/target` a tu Azure App Service.
2. Configura las variables de entorno de la base de datos PostgreSQL desde el portal de Azure.
3. Azure detectará el jar y lo ejecutará automáticamente.

---

### 5. Conexión a la base de datos

Asegúrate de que la base de datos PostgreSQL sea accesible desde el entorno donde vas a desplegar el backend (por ejemplo, una base en Azure Database for PostgreSQL, ElephantSQL, etc).

---

## 🔗 Proyecto principal

- [Repositorio principal de WHS Representaciones](https://github.com/DominidM/whsRepresentaciones)

---

## 📝 Notas

- El backend expone endpoints REST y vistas Thymeleaf.
- Personaliza la configuración según tu entorno de despliegue.
- Recuerda mantener seguras tus credenciales de base de datos (usa variables de entorno o Azure Key Vault si es posible).

---

## 📝 Licencia

Este proyecto sigue la licencia establecida en el repositorio principal.
