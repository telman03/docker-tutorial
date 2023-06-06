Spring boot + Postgre SQL

In a Spring Boot project, the recommended order to run the files would be:

1. Dockerfile: The Dockerfile is used to build a Docker image for your Spring Boot application. You need to run the Dockerfile first to create the Docker image.

2. docker-compose.yml: Once you have the Docker image built using the Dockerfile, you can use the docker-compose.yml file to define and run multiple Docker containers as a service. The docker-compose.yml file typically includes the configuration for your Spring Boot application container as well as any other services or dependencies your application requires (such as a PostgreSQL database).

So, the correct order would be:

1. Run the Dockerfile to build the Docker image:

`docker build -t your-image-name .`

2. Run the docker-compose.yml file to start the containers:

`docker-compose up`
