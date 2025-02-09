# PostgreSQL-practices


## Connect to PostgreSQL Database using SQL Shell & pgAdmin:


## Using SQL Shell:

![alt text](./screenshots/01-psql.png)


## Using pgAdmin:

![alt text](./screenshots/02-pgadmin4.png)



## User Developer Role Creation


![alt text](./screenshots/03-devGroup-role.png)

![alt text](./screenshots/04-devGroup-pass.png)

![alt text](./screenshots/05-devGroup-previleges.png)

![alt text](./screenshots/06-devGroup-membership.png)


## User QA Role Creation


![alt text](./screenshots/08-qaGroupRole-gen.png)

![alt text](./screenshots/09-qaGroupRole-Privileges.png)

![alt text](./screenshots/10-qaGroupRole-Members.png)

![alt text](./screenshots/11-qaGroupRole-SQL.png)



## Command To Create Roles


## postgres Role:

        -- Database: postgres

        -- DROP DATABASE IF EXISTS postgres;

        CREATE DATABASE postgres
            WITH
            OWNER = postgres
            ENCODING = 'UTF8'
            LC_COLLATE = 'English_India.1252'
            LC_CTYPE = 'English_India.1252'
            LOCALE_PROVIDER = 'libc'
            TABLESPACE = pg_default
            CONNECTION LIMIT = -1
            IS_TEMPLATE = False;

        COMMENT ON DATABASE postgres
            IS 'default administrative connection database';


## DEV Role:

        CREATE ROLE "developerRole" WITH
            LOGIN
            SUPERUSER
            CREATEDB
            CREATEROLE
            INHERIT
            REPLICATION
            BYPASSRLS
            CONNECTION LIMIT -1
            PASSWORD 'xxxxxx';
        COMMENT ON ROLE "developerRole" IS 'Full Access to Developers';

## QA Role:
 
        CREATE ROLE "qaRole" WITH
            LOGIN
            NOSUPERUSER
            NOCREATEDB
            NOCREATEROLE
            INHERIT
            NOREPLICATION
            NOBYPASSRLS
            CONNECTION LIMIT -1
            PASSWORD 'xxxxxx';

        GRANT pg_monitor TO "qaRole";
        COMMENT ON ROLE "qaRole" IS 'Read Only Access';


        GRANT "qaRole" TO pg_read_all_data;



## After Role Creation:

![alt text](./screenshots/07-devGroup-afterRole.png)


## Create Database

![alt text](./screenshots/12-CreateDB-Sales.png)

![alt text](./screenshots/13-CreateDB-Definition.png)


