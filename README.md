# MySQL ETL

## Setup (MacOS)

1. Install [Docker Desktop](https://docs.docker.com/desktop/get-started/)
2. Run `mv .env-example` to `.env` and set `MYSQL_ROOT_PASSWORD`
3. Copy the existing source db to `source.sql` in the current directory.
4. Copy the existing target db to `target.sql` in the current directory.
5. Start compose with `docker-compose up`
   
## Loading Data

1. Connect to the database using `docker-compose exec db mysql --host=127.0.0.1 --port=3306 -p`
