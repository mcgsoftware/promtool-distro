# MySQL Design Prompt
Prompt for handling MySQL database schema 
generation. Database design is like OO design, it
works best if you use an iterative process. 

It may seem like it's easier to just jump into java, then the
database will fall out as a byproduct using Spring framework. 
However, you have a cleaner design if you model a normalized database first, 
then the java code that reads and writes into it. 

> Note: There are other tools that could use similar to dbdiagram.io, you can apply this same recipe to other dbms design tools. 
#### Primary use cases

- When designing new services that need new MySQL tables.
- Adding new MySQL schema to exising database. 

#### Solution Recipe
1. Generate DBML markup using GenAI prompt
2. Import DBML into dbdiagram.io tool
3. View the diagrams and add the extra details in dbdiagram.io
4. Generate MySQL sql for schema generation. 
5. Load schema sql into local MySQL instance
6. Use GenAI prompt to generate sql statements to insert a dataset of sample data for your tables.
7. Load tables with the example data and try out some queries to smoke test it. 
8. Iterate over steps 3 to 7 until satisfied.

When done with step 8, export the artifacts into your project Git repo for safe keeping:
 - export dbdiagram.io diagram image into your project design docs.
 - export dbdiagram.io DBML code as a 'schema.dbml' file and save in your project
 - export dbdiagram.io MySQL sql code into a 'schema.sql' file and save in your project.


### Benefits
- It will be easier to design your service code _after_ you model the database schema. 
- Databases have certain constraints and validations that make it more robust and easier to implement services if you leverage them. 
- Nice diagrams that make it easier to design and iterate with.
- Having the schema.sql and schema.dbml, it's easy to update the schema a diagrams for as-built diagrams later on. 
- It's a lot easier to work on persistence if you have accurate diagrams to use. 
- Supports advanced features of MySQL like enum fields, json fields, constraints, etc. 
- DBML is well-documented and easier to use than native schema sql.



