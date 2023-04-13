### Running PostgreSQL Database Inside Docker Container with Docker Compose

In this tutorial, we will explore how to use Docker Compose to run a PostgreSQL database inside a Docker container.

### Prerequisites
Before we begin, please make sure you have the following software installed on your system:

- Docker
- Docker Compose

#### Step 1: Create a Docker Compose file
Create a new file named docker-compose.yml in your project directory and add the following contents:
```yaml
version: '3.3'

services:
  postgres:
    image: postgres:9.6
    restart: unless-stopped
    environment:
      POSTGRES_USER: 'your_user'
      POSTGRES_PASSWORD: 'your_password'
    ports:
      - '5432:5432'
    volumes:
      - ../../../ro:/ro:ro
      - ../../../rw:/rw
      - ../../../Downloads:/dl:ro
      - ../.data/pg96:/var/lib/postgresql/data/
    container_name: pg_0

```

In this file, we define a service called db which will use the postgres Docker image. We also set some environment variables for the database user, password, and name.

Finally, we expose the database port 5432 to the host system by mapping it to the same port on the container.

#### Step 2: Run the Docker Compose file
To start the database, run the following command in your project directory:
```yaml
docker-compose up -d
```
This will start the PostgreSQL container in detached mode, which means it will run in the background.

#### Step 3: Verify the Database is Running
To verify that the database is running, run the following command:
```yaml
docker ps
```
You should see the postgres container listed along with its status and port mappings.

### Conclusion
In this tutorial, we learned how to use Docker Compose to run a PostgreSQL database inside a Docker container. This makes it easy to set up a local development environment for your project without having to install and configure the database software on your machine.
