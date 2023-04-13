You can do this by connecting to your Docker container and accessing the database using a database client tool such as psql or pgAdmin.
To connect to your Docker container, you can use the following command:

```bash
docker exec -it <container_name> bash
```
Replace <container_name> with the name of your Docker container.

Once you are connected to the container, you can use psql to connect to your PostgreSQL database.

Assuming you have psql installed on your Docker container, you can use the following command to connect to your database:

```bash
psql -U <username> -d <database_name>
```
Replace <username> with the username for your database and <database_name> with the name of your database.

Once you are connected to your database, you can use SQL commands to view your tables. For example, you can use the following command to list all the tables in your database:

```bash
\dt
```

You can also use SQL commands to query your tables and view the data they contain. For example, you can use the following command to view all the data in a table:

```sql
SELECT * FROM <table_name>;
```

Replace <table_name> with the name of the table you want to view.

I hope this helps!
