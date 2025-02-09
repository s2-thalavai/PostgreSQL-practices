# PostgreSQL-practices

## Connect to PostgreSQL Database using SQL Shell & pgAdmin:

## Using SQL Shell:

![alt text](./screenshots/01-psql.png)

## Using pgAdmin:

![alt text](./screenshots/02-pgadmin4.png)

## User Role Creation

![alt text](./screenshots/03-group-role.png)

![alt text](./screenshots/04-group-role-1.png)

![alt text](./screenshots/05-group-role-2.png)


## Comnd To Create Role


        CREATE ROLE "developerGroup1" WITH
            LOGIN
            SUPERUSER
            CREATEDB
            CREATEROLE
            INHERIT
            REPLICATION
            BYPASSRLS
            CONNECTION LIMIT -1
            PASSWORD 'xxxxxx';
        COMMENT ON ROLE "developerGroup1" IS 'For Java Developers';

## After Role Creation:

![alt text](./screenshots/06-group-rolle-3.png)
