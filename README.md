# PostgreSQL-practices

## What is PostgreSQL

What is PostgreSQLLet’s start with a simple question: what is PostgreSQL?

PostgreSQL is an advanced, enterprise-class, and open-source relational database system. 
PostgreSQL supports both SQL (relational) and JSON (non-relational) querying.

PostgreSQL is a highly stable database backed by more than 20 years of development by the open-source community.

PostgreSQL is used as a primary database for many web applications as well as mobile and analytics applications.


## History of PostgreSQL

The PostgreSQL project started in 1986 at Berkeley Computer Science Department, University of California.

The project was originally named POSTGRES, about the older Ingres database which was also developed at Berkeley. 
The goal of the POSTGRES project was to add the minimal features needed to support multiple data types.

In 1996, the POSTGRES project was renamed to PostgreSQL to clearly illustrate its support for SQL. 
Today, PostgreSQL is commonly abbreviated as Postgres.

Since then, the PostgreSQL Global Development Group, a dedicated community of contributors continues to make the releases of the open-source and free database project.

Originally, PostgreSQL was designed to run on UNIX-like platforms. 
And then, PostgreSQL evolved to run on various platforms such as Windows, macOS, and Solaris.

## RoadMap

![alt text](postgresql-dba.jpg)


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


# PostgreSQL CREATE DATABASE


        In PostgreSQL, a database is a collection of related data, which serves as a container for tables, indexes, views, and other database objects.

        To create a new database, you use the CREATE DATABASE statement.

        Here’s the basic syntax of the CREATE DATABASE statement:


        CREATE DATABASE database_name
        WITH
            [OWNER =  role_name]
            [TEMPLATE = template]
            [ENCODING = encoding]
            [LC_COLLATE = collate]
            [LC_CTYPE = ctype]
            [TABLESPACE = tablespace_name]
            [ALLOW_CONNECTIONS = true | false]
            [CONNECTION LIMIT = max_concurrent_connection]
            [IS_TEMPLATE = true | false ];


## Create Database

![alt text](./screenshots/12-CreateDB-Sales.png)

![alt text](./screenshots/13-CreateDB-Definition.png)


## Command To Create -- Database: SalesDB

        -- Database: SalesDB

        -- DROP DATABASE IF EXISTS "SalesDB";

        CREATE DATABASE "SalesDB"
            WITH
            OWNER = postgres
            ENCODING = 'UTF8'
            LC_COLLATE = 'English_India.1252'
            LC_CTYPE = 'English_India.1252'
            LOCALE_PROVIDER = 'libc'
            TABLESPACE = pg_default
            CONNECTION LIMIT = -1
            IS_TEMPLATE = False;

