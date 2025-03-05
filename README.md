# Tarea2

## Cómo instalar y ejecutar la aplicación

1. Clona el repositorio:
    ```sh
    git clone https://github.com/tu_usuario/SistemaRecomendacion2025-2.git
    cd SistemaRecomendacion2025-2
    ```
    Esto descarga el código fuente de la aplicación a tu máquina local y te mueve al directorio del proyecto.

2. Configura la base de datos:
    - Asegúrate de tener MySQL instalado y ejecutándose.
    - Crea una base de datos llamada `tarea2`.
    ```sql
    CREATE DATABASE tarea2;
    ```
    Esto prepara el entorno de la base de datos que la aplicación necesita para almacenar y recuperar datos.

3. Configura las propiedades de la aplicación:
    - Abre el archivo [application.properties](http://_vscodecontentref_/2) y ajusta las propiedades de la base de datos según tu configuración local.
    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/tarea2?useSSL=false&serverTimezone=UTC
    spring.datasource.username=tu_usuario
    spring.datasource.password=tu_contraseña
    ```
    Esto asegura que la aplicación pueda conectarse a la base de datos MySQL que configuraste en el paso anterior.

4. Compila y ejecuta la aplicación:
    ```sh
    ./mvnw clean package
    ./mvnw spring-boot:run
    ```
    El primer comando compila el código fuente y empaqueta la aplicación. El segundo comando inicia la aplicación usando Spring Boot.

5. Accede a la aplicación en tu navegador:
    ```
    http://localhost:8081
    ```
    Esto te permite interactuar con la aplicación a través de tu navegador web.

## Cómo desplegar usando Docker

1. Asegúrate de tener Docker y Docker Compose instalados.
    Esto es necesario para construir y ejecutar contenedores Docker.

2. Construye y levanta los contenedores:
    ```sh
    docker-compose up --build
    ```
    Este comando construye las imágenes Docker necesarias y levanta los contenedores definidos en el archivo [docker-compose.yml](http://_vscodecontentref_/3).

3. Accede a la aplicación en tu navegador:
    ```
    http://localhost:8081
    ```
    Esto te permite interactuar con la aplicación a través de tu navegador web, similar a la ejecución local.

4. Para detener los contenedores, ejecuta:
    ```sh
    docker-compose down
    ```
    Este comando detiene y elimina los contenedores, redes y volúmenes creados por `docker-compose up`.
