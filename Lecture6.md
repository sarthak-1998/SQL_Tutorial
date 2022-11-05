SELECT *
FROM <table name1>
INNER JOIN <table name1>
ON <Join condition>;

Sample Command-
SELECT * FROM students2 a INNER JOIN students2 b;


SELECT *
FROM <table name1>
INNER JOIN <table name2>
USING(<column name>);

Sample Command-

SELECT * FROM students2 a INNER JOIN students2 b USING(Name);
SELECT * FROM students2 a INNER JOIN students2 b USING(Marital_Status);
SELECT * FROM students2 a INNER JOIN students2 b USING(Score);



Command for Next Lecture-


CREATE TABLE Actors (
Id INT AUTO_INCREMENT,
FirstName VARCHAR(20) NOT NULL,
SecondName VARCHAR(20) NOT NULL,
DoB DATE NOT NULL,
Gender ENUM('Male','Female','Transgender') NOT NULL,
MaritalStatus ENUM('Married', 'Divorced', 'Single', 'Unknown') DEFAULT "Unknown",
NetWorthInMillions DECIMAL NOT NULL,
PRIMARY KEY (Id));


INSERT INTO Actors (
FirstName, SecondName, DoB, Gender, MaritalStatus, NetworthInMillions)
VALUES ("Brad", "Pitt", "1963-12-18", "Male", "Single", 240.00);

INSERT INTO Actors (
FirstName, SecondName, DoB, Gender, MaritalStatus, NetworthInMillions)
VALUES
("Jennifer", "Aniston", "1969-11-02", "Female", "Single", 240.00),
("Angelina", "Jolie", "1975-06-04", "Female", "Single", 100.00),
("Johnny", "Depp", "1963-06-09", "Male", "Single", 200.00);
INSERT INTO Actors
VALUES (DEFAULT, "Dream", "Actress", "9999-01-01", "Female", "Single", 000.00);
INSERT INTO Actors SET DoB="1950-12-12", FirstName="Rajnikanth",
 SecondName="",  Gender="Male", NetWorthInMillions=50,  MaritalStatus="Married";




 CREATE TABLE DigitalAssets (
          
          URL VARCHAR(200),
          AssetType Enum('Facebook','Twitter', 'Instagram','Pinterest','Website'),
          LastUpdatedOn TIMESTAMP,
          ActorId INT
          );


INSERT INTO DigitalAssets (
     URL, AssetType, LastUpdatedOn, ActorId)
     VALUES
     ("google.com", "Website",  NOW(), 2),
     ("fb.com", "Facebook", NOW(), 3),
     ("insta.c", "Instagram", NOW(), 6),
     ("ttr.com", "Twitter", NOW(), 2),
     ("yahoo.com", "Website", NOW(), 10);

    INSERT INTO DigitalAssets (
    URL, AssetType, LastUpdatedOn, ActorId)
     VALUES
     ("googleee.com", "Website",  NOW(), 11),
     ("facebook.com", "Facebook", NOW(), 5),
     ("insta.com", "Instagram", NOW(), 7),
     ("twitter.com", "Twitter", NOW(), 8),
     ("yahoo.com", "Website", NOW(), 19);





SELECT *
FROM <table name 1>
INNER JOIN <table name 2>
ON {join Condition};


Sample Command -

SELECT * FROM Actors INNER JOIN DigitalAssets ON Actors.Id = DigitalAssets.ActorId;
SELECT * FROM Actors, DigitalAssets WHERE ActorId = Id; // same without inner join

 
SELECT FirstName, DoB, URL FROM Actors, DigitalAssets; //Cartesian Product
SELECT FirstName, DoB, URL FROM Actors INNER JOIN DigitalAssets; // Cartesian Product


SELECT * FROM Actors INNER JOIN DigitalAssets ON URL = FirstName; 
// Independent columns with nothing in common will result in empty set






{Query 1 }
UNION
{Query 2}

Sample command-

SELECT FirstName FROM Actors UNION SELECT URL FROM DigitalAssets;

(SELECT CONCAT (FirstName, ' ', SecondName) AS "Actor Name" From Actors ORDER BY Networthinmillions DESC LIMIT 2)
 UNION 
(SELECT CONCAT (FirstName, ' ', SecondName) AS "Random" From Actors ORDER BY Networthinmillions ASC LIMIT 2);


SELECT FirstName, Id From Actors UNION SELECT Gender FROM Actors; // Error as no. of columns are different in both queries

SELECT FirstName, Id From Actors UNION SELECT Gender, null FROM Actors;
// workaround for unequal columns


SELECT MaritalStatus FROM Actors UNION SELECT Gender FROM Actors; // used as DISTINCT clause

SELECT MaritalStatus FROM Actors UNION ALL SELECT Gender FROM Actors;
// this will give all the entries 





SELECT *
FROM <table name 1>
LEFT [OUTER] JOIN <table name 2>
ON {join condition};


SELECT *
FROM <table name 1>
RIGHT [OUTER] JOIN <table name 2>
ON {join condition};



Sample Command -
SELECT FirstName, Gender, URL, AssetType FROM Actors LEFT JOIN DigitalAssets ON Actors.Id = DigitalAssets.ActorId;

SELECT FirstName, Gender, URL, AssetType FROM DigitalAssets LEFT JOIN Actors ON Actors.Id = DigitalAssets.ActorId;


SELECT FirstName, Gender, URL, AssetType FROM Actors RIGHT JOIN DigitalAssets ON Actors.Id = DigitalAssets.ActorId;


SELECT *
FROM <table name 1>
NATURAL JOIN <table name 2>;



Sample Command-

SELECT FirstName, URL FROM Actors NATURAL JOIN DigitalAssets; // Cartesian Product
SELECT FirstName, URL FROM Actors INNER JOIN DigitalAssets; // Same

ALTER TABLE DigitalAssets CHANGE ActorId Id INT;

 SELECT FirstName, URL FROM Actors NATURAL JOIN DigitalAssets;

SELECT FirstName, URL FROM Actors INNER JOIN DigitalAssets USING(Id);


SELECT FirstName, URL FROM Actors NATURAL LEFT OUTER JOIN DigitalAssets;
SELECT FirstName, URL FROM Actors NATURAL RIGHT OUTER JOIN DigitalAssets;

