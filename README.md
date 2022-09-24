# MySQL ETL

## Setup (MacOS)

1. Install [Docker Desktop](https://docs.docker.com/desktop/get-started/)
2. Run `mv .env-example` to `.env` and set `MYSQL_ROOT_PASSWORD`
3. Copy the existing source db to `source.sql` in the current directory
4. Copy the existing target db to `destination.sql` in the current directory
5. Start compose with `docker-compose up`
   
## Loading Data

1. Modify the `CREATE DATABASE` and `USE` statements in `source.sql` to use the database name `source`
2. Modify the `CREATE DATABASE` and `USE` statements in `destination.sql` to use the database name `source`
3. Drop to a shell inside of the docker container
   
    ```bash
    docker-compose exec /bin/bash
    ```

4. Enter the `/repo` directory from [./docker-compose.yaml](./docker-compose.yaml)

    ```bash
    cd /repo
    ```

4. Connect to the database

    ```bash
    mysql --host=127.0.0.1 --port=3306 -p
    ```

5. Restore the data

    ```mysql
    source source.sql
    source destination.sql
    ```
