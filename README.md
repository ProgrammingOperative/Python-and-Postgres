# Data-Engineer-Tutorial-Series

Convenience PostgreSQL Cheatsheet
===============================
This is a collection of information on PostgreSQL that I tend to use most often.

## TOC
- [Login to the postgresql Options](#login-Options)  
- [ADMINISTRATION](#ADMINISTRATION)
- [Create User, DataBase and Attach permission to this user](#Creating-user-and-database-and-grant-access-to-created-user)
- [Common Commands](#Common-Commands)

### Login to the postgresql Options
- Directly accessing the psql using the default superuser postgres
	 `sudo -u postgres psql`

- Peer authentication which uses the os credentials
	identical (or fully match) to the OS account, with an optional name mapping defined in pg_ident.conf file. ident is applicable to TCP/IP; while peer for "local" connection.

	`psql -U wacira db_name`

- md5: require md5-hashed password
	`psql -U master -h localhost -p 5433 testdb`

### ADMINISTRATION
- CREATE ROLES
	`CREATE ROLE role_name;`

- ALTER ROLE WITH PRIVILEDGES
	`ALTER ROLE role_name WITH CREATEDB, CREATEROLE, SUPERUSER, CREATEVIEW`

- GRANT ROLE TO USER
	`GRANT role_name TO user_name`

- REVOKE ROLE FROM USER
	`REVOKE role_name FROM user_name`

- DROP ROLE 
	`DROP ROLE role_name;`

- CREATE USER
	`CREATE USER user_name WITH priviledge_names`


- DROP USER
	`DROP USER user_name;`


- CREATE A DATABASE
	`CREATE DATABASE database_name;`


#### Creating user and database and grant access to created user

`CREATE DATABASE yourdbname;`
`CREATE USER youruser WITH ENCRYPTED PASSWORD 'yourpass';`
`GRANT ALL PRIVILEGES ON DATABASE yourdbname TO youruser;`

### Common Commands

- for doing admin type things such as managing db users, log in as the postgres user: `psql postgres;`

- to connect when starting psql use the `-d` flag like: `psql -d nyc_noise`

- to list all databases: `\l`

- to quit psql: `\q`

- To get information about current connection from the psql command prompt: `\conninfo`

- To change user: `\c - a_new_user`

