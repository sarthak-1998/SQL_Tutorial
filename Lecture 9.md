CREATE VIEW <view name> AS
SELECT * FROM <table name> 
WHERE {conditions ...};


Sample Command-

CREATE VIEW AssetsCount AS
    -> SELECT Id, COUNT(AssetType) AS Number
    -> FROM DigitalAssets 
    -> GROUP BY Id;


    SHOW FULL TABLES; //to check tables and views in a DataBase


CREATE VIEW ActorAccounts AS
    -> SELECT FirstName, SecondName, URL 
    -> FROM Actors
    -> NATURAL JOIN DigitalAssets ; // view from multiple tables

SELECT * FROM ActorAccounts;


CREATE VIEW ActorsURL AS SELECT FirstName, URL FROM ActorAccounts; 
//view from another view

SELECT * FROM ActorsURL;




UPDATE <view name>
SET <column 1> = <value 1>, <column 2> = <value 2>...
WHERE {conditions...};


Sample Command -

CREATE VIEW ActorView AS 
    -> SELECT Id, FirstName, SecondName, NetWorthInMillions 
    -> FROM Actors;

    SELECT * FROM ActorView;

    UPDATE ActorView 
    -> SET Networthinmillions = 100 WHERE Id = 5;

    SELECT * FROM Actors;
//updated the data in view and its underlying table


SELECT Table_Name, is_updatable 
    -> FROM information_schema.views
    -> WHERE table_schema = 'TESTDB';
// to check view which are updatable 


DELETE FROM ActorsURL WHERE FirstName = 'DREAM';
// error expected because of join 



DELETE FROM ActorView WHERE Id = 5;

SELECT * FROM Actors; // to confirm the deletion




SHOW FULL TABLES ; //view all the tables and views

SHOW FULL TABLES 
WHERE table_type = 'VIEW'; // only lists views


SELECT table_name 
FROM information_schema.TABLES
WHERE table_type = 'VIEW'
AND table_schema = '<name of the Database>';

Sample command -

SELECT table_name FROM information_schema.TABLES WHERE table_type = 'VIEW' AND table_schema = 'testdb' ;


DROP VIEW <view name 1>, <view name 2>.... ;

DROP VIEW IF EXITS <view name 1>, <view name 2>....;


Sample command -

DROP VIEW random, test;        
DROP VIEW IF EXISTS test2, viewtest;



RENAME TABLE <current view name>
TO <new view name>;

Sample Command -

RENAME TABLE ActorsURL TO ActorsURLs; 