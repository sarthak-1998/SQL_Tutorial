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

CREATE TABLE <Table Name>(
    Column 1 <Datatype>,
    column 2 <Datatype>,
    .
    .

); 


CREATE TABLE PERSON(
    -> Name VARCHAR(15),
    -> DOB DATE,
    -> GENDER ENUM ('Male','Female','Others'),
    -> MaritalStatus ENUM('Single','Married'),
    -> Salary DECIMAL);
    
  
  INSERT INTO <table name>(<Column name 1>,<Column name 2>....)
  VALUES (<Value 1>,<Value 2>....);


  Sample Command - 
  INSERT INTO students (Name, ID) 
    -> VALUES ("Sarthak","9988");


Sample Command -

INSERT INTO students2 (ID, Name, DOB, MaritalStatus, Score)  VALUES (DEFAULT, "Sarthak Jain", "1998-04-24","Single",50.00);


Sample Command -

INSERT INTO students2 (ID, Name, DOB, MaritalStatus, Score)  
VALUES 
(DEFAULT, "Sarthak Jain", "1998-04-25","Single",50.00),
(DEFAULT, "Sam Jain", "1998-04-26","Married",60.00),
(DEFAULT, "Kevin", "1998-04-27","Single",70.00),
(DEFAULT, "Sanket", "1998-04-28","Married",80.00);




INSERT INTO <table name>()
Values <>() 

// Enter NULL  values to the table




