Dockerizing a Spring Boot application with Swagger/OpenAPI documentation involves creating a Docker image of your application and running it in a Docker container. Here are the general steps you can follow:

1. Create a Dockerfile in the root directory of your Spring Boot project. A Dockerfile is a script that contains instructions on how to build a Docker image for your application. Here is an example Dockerfile:
  ```dockerfile
  FROM openjdk:17
  VOLUME /tmp
  ADD target/myapp.jar app.jar
  ENTRYPOINT ["java","-jar","/app.jar"]
  ```
    
  This Dockerfile specifies that we want to use the `openjdk:17` base image, create a volume for the /tmp directory, add our application's JAR file to the image, and specify the entrypoint to be the command that runs our application.
  
 2. Build the Docker image by running the docker build command in the directory where your Dockerfile is located. For example, if your Dockerfile is located in the root directory of your project, you would run the following command:
  ```bash
  docker build -t myapp .
  ```
  This command will create a Docker image with the tag myapp using the Dockerfile in the current directory.
  
 3. Run the Docker container by running the docker run command followed by the name of the Docker image you just created. For example, to run the myapp image, you would run the following command:
   ```bash
   docker run -p 8080:8080 myapp
   ```
  This command maps port 8080 on the container to port 8080 on the host, and runs the container using the myapp image. 
 
 4. Once your container is running, you can access the Swagger/OpenAPI documentation by navigating to http://localhost:8080/swagger-ui.html in your web browser.


I hope this helps! Let me know if you have any further questions.



