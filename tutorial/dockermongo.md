#### Step 1: Create a Docker Compose file
Create a new file in your project directory called docker-compose.yml. This file will contain the instructions for docker-compose to set up and run MongoDB.

```yaml
version: '3.7'
services:
  mongo:
    image: mongo:latest
    container_name: mongo
    restart: always
    ports:
      - '27017:27017'
    volumes:
      - './data:/data/db'
```

This YAML file defines a single service called `mongo`, which uses the latest MongoDB image from Docker Hub. The `container_name` property specifies the name of the container that `docker-compose` will create, and the `restart` property ensures that the container will be automatically restarted if it stops for any reason.

The `ports` section maps the container's default MongoDB port (`27017`) to the same port on your host machine. This allows you to connect to the MongoDB instance from your local machine.

Finally, the `volumes` section maps a directory on your host machine (`./data`) to the `/data/db` directory inside the container. This allows MongoDB to persist data between container restarts.

#### Step 2: Start the container
To start the MongoDB container, run the following command in your terminal:

```yaml
docker-compose up -d
```
This command will build the MongoDB image if it doesn't already exist, create a new container based on the image, and start the container in detached mode (`-d`). You should see output similar to the following:
```yaml
Creating mongo ... done
```

#### Step 3: Verify the container is running
To verify that the MongoDB container is running, run the following command:

```yaml
docker ps
```

You should see output similar to the following:

```bash
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                      NAMES
8ba31e21943a   mongo:latest   "docker-entrypoint.s…"   25 seconds ago   Up 23 seconds   0.0.0.0:27017->27017/tcp   mongo
```


The STATUS column should show Up for the MongoDB container.

#### Step 4: Connect to MongoDB
To connect to the MongoDB instance running inside the Docker container, you can use a MongoDB client such as the mongo shell or a GUI tool like Robo 3T.

In the client, you can connect to the MongoDB instance using the following URL:
```
mongodb://localhost:27017/
```
This URL specifies the default MongoDB port (`27017`) on your local machine.

Congratulations! You now have MongoDB running inside a Docker container using docker-compose.
