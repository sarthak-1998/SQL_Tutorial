
Nested Queries-

{Query1 ({Query 2})};


Sample Command-

SELECT URL FROM DigitalAssets WHERE AssetType = "Website" AND Id = (SELECT Id From Actors WHERE FirstName = "Jennifer");


SELECT FirstName FROM actors INNER JOIN DigitalAssets ON Actors.Id = DigitalAssets.Id WHERE DigitalAssets.LAstUpdatedOn = (SELECT MAX(LastUpdatedOn) FROM DigitalAssets);






Nested Queries-

{Query1 ({Query 2})}; // result will have a set of rows for a column

ANY Clause - Match with any of the values from a set
IN CLause - Same as ANY
ALL Clause - Where you want to match with all the row values from that table

Sample Command-

 SELECT * FROM Actors INNER JOIN DigitalAssets USING(Id) WHERE AssetType = ANY(SELECT DISTINCT AssetType FROM DigitalAssets WHERE AssetType != 'Website');

 SELECT * FROM Actors INNER JOIN DigitalAssets USING(Id) WHERE AssetType != 'Website';


 SELECT FirstName FROM Actors WHERE Id = ANY(SELECT Id FROM DigitalAssets WHERE AssetType = 'Facebook'); //ANY Clause

 SELECT FirstName FROM Actors WHERE Id IN (SELECT Id FROM DigitalAssets WHERE AssetType = 'Facebook');  // IN Clause


 SELECT FirstName FROM Actors WHERE NetWorthInMillions > ALL (SELECT NetWorthInMillions FROM Actors WHERE FirstName LIKE "R%"); // ALL Clause 






Nested Row Queries 

{Query1 ({Query 2})}; // result will have multiple rows for multiple columns

Sample Command -

SELECT Firstname FROM Actors INNER JOIN DigitalAssets USING(Id) WHERE MONTH(DoB) > MONTH(lastupdatedon) OR DAY(DoB) > DAY(Lastupdatedon);



SELECT FirstName, AssetType, LastUpdatedOn FROM Actors INNER JOIN (SELECT Id, AssetType, LAstUpdatedON FROM DigitalAssets) as tbl USING(Id);

SELECT FirstName, AssetType, LastUpdatedOn FROM Actors INNER JOIN (SELECT Id, AssetType, LAstUpdatedON FROM DigitalAssets) as tbl USING(Id) WHERE FirstName = "Jennifer";

SELECT FirstName, AssetType, LastUpdatedOn FROM Actors INNER JOIN (SELECT Id, AssetType, LAstUpdatedON FROM DigitalAssets) as tbl USING(Id) WHERE FirstName = "Jennifer" ORDER BY LastUpdatedOn DESC LIMIT 1;





