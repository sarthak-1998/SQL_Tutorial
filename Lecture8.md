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
  