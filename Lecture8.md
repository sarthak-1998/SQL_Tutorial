EXISTS - To check if the value exist or not\


Sample  Command-

 SELECT * FROM Actors WHERE EXISTS(SELECT * FROM DigitalAssets WHERE URL LIKE "%com");
 // Entire table

 SELECT * FROM Actors WHERE EXISTS(SELECT * FROM DigitalAssets WHERE URL LIKE "%in");
 // empty set


 NOT - Compliment

 Sample Command -

 SELECT * FROM Actors WHERE NOT EXISTS (SELECT * FROM DigitalAssets WHERE URL LIKE "%com%"); // empty set

  SELECT * FROM Actors WHERE NOT EXISTS (SELECT * FROM DigitalAssets WHERE URL LIKE "%in"); // entire table





Old Syntax-

DELETE <table 1>, <table 2>
FROM <table 1>, <table 2>, <table 3>
WHERE {conditions...}


New Syntax -

DELETE FROM <table 1>, <table 2>
USING <table 1>, <table 2>, <table 3>
WHERE {condition...}




Sample Command -

DELETE Actors, DigitalAsssets 
FROM Actors 
INNER JOIN DigitalAssets
USING(Id)
WHERE AssetType = "Twitter";

DELETE FROM Actors, DigitalAssets
USING Actors
INNER JOIN DigitalAssets
USING(Id)
WHERE AssetType = "Twitter"; //will work same as above 


1) -- specify the tables to delete from
2) -- mention reference tables
3) -- conditions to narrow down rows




UPDATE <table 1>, <table 2>
SET <column name 1> = {new value}, <column name 2> = {new value}
WHERE {conditions ...}


Sample Command -

UPDATE Actors 
INNER JOIN DigitalAssets
USING(Id)
SET FirstName = UPPER(FirstName), SecondName = UPPER(SecondName), URL = LOWER(URL)
WHERE AssetType = "Instagram";


UPDATE Actors, DigitalAssets
SET FirstName = UPPER(FirstName), SecondName = UPPER(SecondName), URL = LOWER(URL)
WHERE AssetType = "Facebook"
AND Actors.Id = DigitalAssets.Id;




In case of Existing Table -

INSERT INTO <table name 1>(<Column name1>, <column name 2>...)
SELECT <column name 3>, <column name 4>
FROM <table name 2>;



Sample Command -

CREATE TABLE Names (name VARCHAR(20), Primary Key(name));
//Pre requesite

INSERT INTO Names(name)
SELECT SecondName FROM Actors;




In case of New Table - 

CREATE TABLE <New table name>( <column name 1> <data type>, <column name 2> <data type>...)
SELECT <column name 3>, <column name 4> 
FROM <table name>;



Sample command -

CREATE TABLE TempActors SELECT * FROM Actors;


CREATE TABLE CopyActor LIKE Actors ; 
 // only copies the schema of table and skips the data 



 REPLACE INTO <table name>( <column 1>, <column 2>...)
 VALUES ( <value 1>, <value 2>...)
 WHERE {condition ...};


 Sample Command -

  REPLACE INTO Actors (Id, FirstName, SecondName, DoB, Gender, MaritalStatus, NetWorthInMillions) VALUES (3,"George","Clooney","1962-05-06","Male","Married",500.00);


  REPLACE INTO Actors (Id) VALUES(3); // Create a row with null values

  REPLACE INTO Actors SET Id = (SELECT Id FROM Actors WHERE FirstName = "Brad");
  // error expected as reading from same table in sub query is not allowed

