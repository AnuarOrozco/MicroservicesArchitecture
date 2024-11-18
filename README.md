# Arquitectura de Microservicios del Proyecto
![Arquitectura](https://github.com/user-attachments/assets/44d7d38f-9646-41c0-a0ec-89bd38b62bbf)

## Descripción General

El proyecto está compuesto por cinco microservicios diseñados bajo una arquitectura de microservicios, cada uno con responsabilidades específicas. Los usuarios interactúan con los microservicios a través de un **API Gateway**, que actúa como punto de entrada centralizado.

---

## Microservicios Principales

### 1. **API Gateway**
El **API Gateway** es el encargado de recibir las peticiones de los usuarios y redirigirlas al microservicio correspondiente. Este componente centraliza y facilita la comunicación, manejando las rutas y solicitudes externas.

- **Rutas disponibles:**
  - `/api/courses`: Redirige al microservicio de **Courses**.
  - `/api/students`: Redirige al microservicio de **Students**.

### 2. **Courses**
El microservicio **Courses** es responsable de gestionar toda la información relacionada con los cursos.

- **Base de datos**: PostgreSQL.
- **Comunicación**: Puede interactuar con el microservicio **Students** mediante peticiones HTTP REST.

### 3. **Students**
El microservicio **Students** se encarga de administrar los datos relacionados con los estudiantes.

- **Base de datos**: MySQL.
- **Comunicación**: Puede interactuar con el microservicio **Courses** mediante peticiones HTTP REST.

Ambos microservicios están diseñados para ser independientes, pero pueden colaborar directamente cuando sea necesario.

---

## Microservicios de Configuración

### 4. **Eureka**
Eureka es un servicio de descubrimiento utilizado para registrar y gestionar los microservicios de manera dinámica.

- **Función principal**: Almacenar las direcciones IP y puertos de los microservicios registrados.
- **Ventaja**: Permite que los microservicios se registren automáticamente y facilita su localización en la red sin necesidad de configuraciones manuales.

### 5. **Config Server**
El **Config Server** es un servicio centralizado de configuración que gestiona los archivos de configuración de todos los microservicios.

- **Función principal**: Proveer configuraciones externas a los microservicios de forma dinámica.
- **Ventaja**: Permite realizar cambios en las configuraciones sin necesidad de desplegar nuevamente los microservicios, mejorando la flexibilidad y el mantenimiento del sistema.

---

## Conexión entre Microservicios
Cada microservicio tiene su propia base de datos, lo que garantiza la independencia y escalabilidad del sistema. Además, la comunicación entre microservicios se realiza mediante el protocolo HTTP REST, facilitando la interoperabilidad y flexibilidad en el sistema.

## Instancias de Microservicios en Eureka
![eureka test instances](https://github.com/user-attachments/assets/969ac761-e9f6-4bc4-a5cc-3c83869eeafc)

