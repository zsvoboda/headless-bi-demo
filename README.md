# Headless BI demo 

* [Demo script document](https://docs.google.com/document/d/1cykrZoyS7mj_rHSQdLDht4mhYidscok3Jv-FhSFOE4Q/edit#)
* [Demo deck](https://docs.google.com/presentation/d/1kCe_0dp1Z481klcW8SfOhuLuKgy58p7fwjDMSkN_uoo/edit#slide=id.g7e01633636_0_414)

## Creating Postgres DB
There are two options how to load data to your POstgres database.

### DBeaver
1. Connect to your Postgres from the DBeaver
2. Execute the ``sql/pgsql_tables.sql``
3. Import data to the tables that the script creates (select tables and right-click) from the corresponding CSV files in the ``data`` directory
4. Execute the ``sql/pgsql_constraints.sql`` script

### pg_restore
The database has been dumped with this command:
 
 ``pg_dump --host=localhost --port=5432 --user=demouser --compress=9 --file=insurance.dump --format=c --schema=insurance demo``

 You can restore it using this command:

  ``pg_restore --host=localhost --port=5432  --dbname=demo insurance.dump``

## Requirements
Install Visual Studio Code and the _Rest Client_ extension.

## Invoking GoodData.CN REST APIs
Open the ``./api/rest.http`` file in the VSCode editor and clisk on the _Send Request_ link on top of each request. 

## REST calls sequence

1. Create workspace
2. Create Postgres connection
3. Publish semantic model
4. Publish metrics or analytical model