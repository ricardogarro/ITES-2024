# ITES-2024

# Trabajo Práctico: Desarrollo y Despliegue de una Aplicación Web con Docker y Backend a Elección

## Objetivo:
Desarrollar una página web estática utilizando HTML y CSS, con un backend que procese las solicitudes de suscripción y consultas de clientes. Los datos ingresados por los usuarios se almacenarán en una base de datos MySQL o MariaDb, y la gestión de esta base de datos se realizará a través de phpMyAdmin. Todo el proyecto deberá estar contenerizado utilizando Docker. Cda grupo podrá elegir la tecnología de backend que prefieran. El trabajo se realizará en grupos de dos personas.

## Descripción del Trabajo:

### 1. Frontend:
Desarrollar una landing page que cumpla con los siguientes requisitos:

- **Header**: Incluir un menú de navegación con enlaces a las diferentes secciones.
- **Sección principal**: Mostrar una imagen destacada y una breve descripción del propósito del sitio web.
- **Servicios**: Describir al menos tres servicios o características del sitio.
- **Formulario de suscripción/información**:
  - Debe incluir los siguientes campos:
    - Nombre
    - Correo electrónico
    - Teléfono (opcional)
    - Mensaje (para que el cliente pueda dejar una consulta)
- **Footer**: Mostrar la información de contacto y enlaces a redes sociales.

El servidor web que sirva el frontend debe estar contenerizado utilizando Docker. (puede implelementar nginx o apache segun prefiera)

### 2. Backend:
El backend será desarrollado con la tecnología a elección del grupo. Algunas de las tecnologías recomendadas pero no exluyentes pueden ser:

- C# (ASP.NET Core)
- Python (Flask/Django)
- PHP (Laravel/Slim)
- Go
- Node.js (Express)

El backend debe exponer un único endpoint para manejar las solicitudes del formulario:

- **POST `/submit-client-data`**: Este endpoint recibirá los datos ingresados en el formulario y los almacenará en la base de datos MySQL.

Los datos deben ser almacenados en la tabla `client_requests` con la siguiente estructura:

- `id`: Clave primaria auto-incremental.
- `name`: Nombre del cliente.
- `email`: Correo electrónico del cliente.
- `phone`: (Opcional) Número de teléfono del cliente.
- `message`: Consulta o mensaje enviado por el cliente.
- `created_at`: Fecha y hora de creación del registro.

El backend debe estar contenerizado utilizando Docker.

### 3. Base de Datos MySQL o MariaDb y phpMyAdmin:
- Configurar un contenedor Docker para **MySQL** o **MariaDb**  que almacenará los datos ingresados por los clientes.
- Configurar un contenedor Docker para **phpMyAdmin** que permitirá gestionar visualmente la base de datos.
- La base de datos debe ser inicializada con la tabla `client_requests`.

### 4. Versionado con Git:
- El proyecto debe utilizar **Git** para el control de versiones.
- Cada equipo debe crear un repositorio en **GitHub**.
- Se espera que los commits sean frecuentes y que contengan mensajes descriptivos y claros.
- Cada integrante del equipo debe trabajar en **branches** separadas para distintas funcionalidades y crear **pull requests** para integrar el trabajo colaborativamente.

### 5. Docker:
- Todo el proyecto debe estar contenerizado, incluyendo:
  - El servidor web que sirva el frontend.
  - El backend en la tecnología elegida.
  - La base de datos MySQL.
  - phpMyAdmin.
- Crear un archivo `docker-compose.yml` que defina todos los servicios mencionados.
- El entorno de desarrollo debe poder levantarse con un solo comando utilizando **Docker Compose**.

### 6. Documentación:
El proyecto debe incluir un archivo `README.md` que describa:

- La funcionalidad del proyecto.
- Las instrucciones para clonar el repositorio.
- Los pasos para levantar el entorno con Docker.
- Descripción de las tecnologías utilizadas.
- Ejemplos de las rutas del backend y las respuestas esperadas.

## Criterios de Evaluación:

### Frontend:
- Estructura del HTML bien organizada.
- Estilos de CSS bien implementados.

### Backend:
- Funcionamiento correcto del backend en la tecnología elegida.
- Manejo adecuado de las solicitudes del formulario.
- Almacenamiento correcto en la base de datos.

### Docker:
- Todo el proyecto debe estar contenerizado correctamente.
- Uso adecuado de Docker para contenerizar el frontend, backend y la base de datos.
- Configuración de Docker Compose para levantar todo el entorno.

### Versionado con Git:
- Uso adecuado de Git con commits frecuentes y descriptivos.
- Correcto uso de branches y pull requests.

### Documentación:
- El `README.md` debe ser claro, con instrucciones completas para ejecutar el proyecto y describir el flujo de trabajo.

### Estructura de Directorios Sugerida:

# Estructura del Proyecto

```plaintext
/<nombre-del-proyecto>
|
├── frontend                 # Carpeta para el frontend (HTML, CSS, JS)
│   ├── Dockerfile            # Dockerfile para contenerizar el frontend
│   ├── index.html            # Archivo principal HTML
│   ├── assets               # Carpeta para recursos como imágenes, fuentes, etc.
│   │   ├── styles.css        # Archivo CSS principal
│   │   └── script.js         # (Opcional) Archivo JS si se requiere
│   └── img                  # Carpeta para imágenes
|
├── backend                  # Carpeta para el backend
│   ├── Dockerfile            # Dockerfile para contenerizar el backend
│   ├── src                  # Código fuente del backend (varía según la tecnología)
│   │   ├── app.py            # Si es Flask
│   │   ├── server.js         # Si es Node.js, por ejemplo
│   │   ├── main.go           # Si es Go, etc.
│   └── requirements.txt      # Si es Python (o archivo equivalente para otras tecnologías)
|
├── database                 # Carpeta para inicialización de la base de datos
│   ├── init.sql              # Script de inicialización para crear la tabla `client_requests`
|
├── docker-compose.yml       # Archivo Docker Compose para definir todos los servicios
|
├── README.md                # Archivo README con instrucciones del proyecto
|
└── docs                     # Documentación adicional del proyecto (opcional)
    └── project-description.md # Descripción detallada del proyecto o guía de uso.



## Opcional 
- Implementar diseño responsivo que se adapte a dispositivos móviles.
- Implementar animaciones CSS para mejorar la interacción del usuario.
- Desplegar el sitio en un servicio de hosting gratuito como **GitHub Pages** o utilizar **Docker Hub** para compartir las imágenes de Docker del proyecto.

## Entrega:
- El repositorio debe ser compartido en **GitHub** con el docente.
- Todo el entorno debe funcionar correctamente y demostrar la integración completa del frontend, backend y base de datos mediante Docker.

```plaintext
