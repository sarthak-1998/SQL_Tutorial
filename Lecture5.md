SELECT <column name>
FROM <table name>
GROUP BY <column name>;
...


Sample Command-

SELECT Name FROM students2 GROUP BY Name;

SELECT Name, COUNT(*) FROM students2 GROUP BY Name;

SELECT Marital_Status, AVG(Score) FROM students2 GROUP BY Marital_Status;

SELECT Name, AVG(Score) FROM students2 GROUP BY Name ORDER BY Name;

SELECT Name, Score FROM students2 GROUP BY Name; // Not Allowed (Error expected)




SELECT <column name>, {Aggreagate functions}
FROM <table name>
GROUP By <column name>
HAVING {Conditions};
...


Sample Command - 

 SELECT Name, AVG(Score) as Average FROM students2 GROUP BY Name Having Average>70;
 
 SELECT Marital_Status, COUNT(*) AS Number FROM students2 GROUP BY Marital_Status HAVING Number>2;

 SELECT Marital_Status, COUNT(*) AS Number FROM students2 GROUP BY Marital_Status HAVING Number>3;

 SELECT Marital_Status, COUNT(*) AS Number FROM students2 GROUP BY Marital_Status HAVING Number>5;

 SELECT Marital_Status, AVG(Score) AS Average FROM students2 GROUP BY Marital_Status HAVING Marital_Status = "Married";

  SELECT Marital_Status, AVG(Score) AS Average FROM students2 WHERE Marital_Status = "Married" GROUP BY Marital_Status; 
  // Same query as above using where instead of Having clause. Same output



