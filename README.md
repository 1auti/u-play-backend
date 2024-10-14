### API U-Play
Este es el backend para API U-Play, una aplicación basada en Spring Boot que proporciona servicios para gestionar usuarios, preguntas, transacciones, y carteras de criptomonedas. La aplicación utiliza PostgreSQL como base de datos y está configurada con JPA para la persistencia de datos.

# FRONTEND: https://github.com/1auti/u-play-frontend
## Tecnologías utilizadas
Java 17
Spring Boot 3.2.2
Maven
PostgreSQL
Hibernate / JPA
JWT (Json Web Token) para autenticación
Apache Commons Lang para utilidades adicionales
Prerrequisitos
Asegúrate de tener instalados los siguientes componentes:

JDK 17
Maven
PostgreSQL
Instalación
Clona este repositorio en tu máquina local:
bash
Copy code
git clone https://github.com/tuusuario/api-u-play.git
cd api-u-play
Configura tu base de datos PostgreSQL local y actualiza los detalles de conexión en el archivo application.properties:
properties
Copy code
# Configuración de la base de datos PostgreSQL
spring.datasource.url=jdbc:postgresql://localhost:5432/uplay
spring.datasource.driverClassName=org.postgresql.Driver
spring.datasource.username=postgres
spring.datasource.password=admin

# Mostrar las consultas SQL en la consola
spring.jpa.show-sql=true
Compila y ejecuta el proyecto utilizando Maven:
bash
Copy code
mvn clean install
mvn spring-boot:run
Endpoints principales
Usuarios
Registro de usuario:
POST /api/users/register
Registra un nuevo usuario.

Iniciar sesión:
POST /api/users/login
Devuelve un token JWT si las credenciales son válidas.

Obtener información del usuario:
GET /api/users/data/{userId}
Retorna la información completa de un usuario por su ID.

Modificar saldo de monedas:
PUT /api/users/update-coin-balance/{userId}?newCoinBalance={balance}
Actualiza el saldo de monedas de un usuario.

Preguntas
Obtener todas las preguntas:
GET /api/questions/getQuestions
Devuelve una lista de preguntas.

Obtener pregunta por usuario:
POST /api/questions/getUserQuestion
Devuelve una pregunta asociada a un usuario en particular usando su correo electrónico.

Transacciones
Intercambio de monedas:
POST /api/users/exchange-coins
Permite a un usuario intercambiar monedas por criptomonedas.

Obtener transacciones del usuario:
GET /api/users/transactions/{userId}
Devuelve un historial de transacciones de un usuario.

Configuración JWT
Este proyecto utiliza JWT para la autenticación. El token se genera durante el inicio de sesión y se devuelve en la respuesta. Los clientes deben incluir este token en los encabezados de las solicitudes para acceder a los endpoints protegidos.

Base de datos
La estructura de la base de datos se gestiona mediante JPA y Hibernate. La aplicación crea y actualiza automáticamente las tablas según las entidades definidas. Los scripts de inicialización se encuentran en el archivo data.sql.

Contribuciones
Si deseas contribuir a este proyecto, por favor sigue estos pasos:

Haz un fork del proyecto.
Crea una nueva rama (git checkout -b feature-nueva-funcionalidad).
Haz commit de tus cambios (git commit -am 'Añadí una nueva funcionalidad').
Sube la rama (git push origin feature-nueva-funcionalidad).
Abre un Pull Request.
Licencia
Este proyecto está bajo la licencia MIT.