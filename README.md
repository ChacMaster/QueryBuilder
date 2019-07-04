# QueryBuilder
Query Builder and Viewer for Progress databases. 

## Getting started
### Quick install
- Create a folder 'QueryBuilder' and extract all files in it
- Open a Proenv session in 'QueryBuilder\bin'
- Run the command file 'create_db.cmd' and close the Proenv session

### Run QueryBuilder
You can either start QueryBuilder by double clicking 'QueryBuilder\QueryBuilder.pf' or by opening a Progress GUI Procedure Editor window, connect to the QueryBuilder database, add the QueryBuilder folder to the propath and then execute:
```
RUN wMyQueries.w 
```

This will start the main window:

![](docs\MyQueries.png)


## Database info
The folder 'db' contains the files to create a database. The file 'create_db.cmd' will create a queryBuilder database file for you, together with a copy of the Sports2000 database. Run it from within a ProEnv command session. Alternatively you can create a database yourself or load the .df into your own database. There are 3 tables in this database:

- qbQuery: holds info about the query itself, 1 record for each query
- qbTable: holds info for each table that is used in the query
- qbField: holds info for each field in the query

The tables are linked to each other via the field queryNr. This field is populated using a sequence.

## Special notes
### User types
The programs rely on the user being one of the following types:
- normal
- admin
- superadmin

Currently, this is implemented in a minimal way since it should be part of the host application to set the user's level. This is implemented in the program 'queryLib.p'. Look for the variable gcUserType and the functions setUserType and getUserType.

### Forbidden tables and fields
In the src folder you will find 3 files whose name look like 'SchemaRestrictions-*.txt' with the user type at the place of the asterisk. In this file you can specify the tables and fields the user of that type should not have access to. Even for superAdmins, there may be tables you do not want them to mess with. 









