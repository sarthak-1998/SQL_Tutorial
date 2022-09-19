// In today's class we will try to understand about databases
Notes Github Link - https://github.com/sarthak-1998/SQL_Tutorial

To check what all databases are present on my system -
SHOW DATABASES; 

To create a new database -
CREATE DATABASE <NAME>;

Select a database to work on that -
USE <DATABASE NAME>;

To delete a database -
DROP DATABASE <DATABASE NAME>;



// How to create a table in a database

CREATE TABLE <Table Name>
(
    Column1 <Datatype>,
    Column2 <Datatype>,
    .
    .
    .
);


To understand the description of the table 

DESC <Table Name>;

CREATE TABLE <Table Name>(
    Column1 <Datatype>,
    Column2 <Datatype>  NOT NULL,
    .
    .

);