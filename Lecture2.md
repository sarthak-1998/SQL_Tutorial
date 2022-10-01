SELECT <Column name 1>, <Column name 2>....
FROM <Table name>;


SELECT * FROM <Table Name>;


SELECT * FROM <Table Name>
WHERE <Column name 1> =/</> "Value 1";


Sample Command - 
SELECT * FROM students2 
    -> WHERE Score = 50;


SELECT * FROM <table name>
 Where <Column name> LIKE "%String%"


 Sample Command -

 SELECT * FROM students2 Where Name LIKE "Sarthak Jain";
 SELECT * FROM students2 Where Name LIKE "%Jain";


 SELECT * FROM <table name>
 Where <column name> LIKE "_String%";

 Sample Command -

 SELECT * FROM students2 Where Name LIKE "_e%";
 SELECT * FROM students2 Where Name LIKE "%";


 SELECT * FROM <table name>
 WHERE {Comparisson} AND / OR {Comparisson};


//
 Comparisson -> <column name 1> = <some value>
 -> <column name 2> >/ < />= /<= <value>


 Sample Command -
 SELECT * FROM students2  WHERE MaritalStatus = "Married" AND Score > 50;

 SELECT * FROM students2  WHERE MaritalStatus = "Single" OR Score = 60;



 SELECT * FROM students2 
 WHERE NOT <column name> = <value>


 Sample Command - 
SELECT * FROM students2  WHERE NOT Score = 60;

SELECT * FROM students2  WHERE NOT MaritalStatus = "Single";

SELECT * FROM students2  WHERE (MaritalStatus = "Single" AND Score = 70) OR (MaritalStatus = "NA" OR Score = 80);




SELECT * FROM <table name>
WHERE {Comparisson}
ORDER BY <coulmn name>;


Sample Command -
SELECT * FROM students2 ORDER BY Name;
SELECT * FROM students2 ORDER BY MaritalStatus;
SELECT * FROM students2 ORDER BY MaritalStatus, Name;

SELECT * FROM <table name>
Where { Comparisson}
ORDER BY <column name> ASC/ DESC;   //Ascending or Descending order

Sample Command - 
SELECT * FROM students2  Where Score >50 ORDER BY Name DESC;


SELECT * FROM students2 ORDER BY Score DESC, Name ASC;
SELECT * FROM students2 ORDER BY Score DESC, DOB DESC;





SELECT * FROM <table name>
WHERE {comparisson}...
ORDER BY <column name>...
LIMIT <value>;


Sample Command -

SELECT * FROM students2 ORDER BY Score DESC LIMIT 3;


SELECT * FROM <table name>
WHERE {comparisson}..
ORDER BY <column name>...
LIMIT <value>
OFFSET <value>;


Sample command -
SELECT * FROM students2 ORDER BY Score DESC LIMIT 1 OFFSET 3;

SELECT * FROM students2 ORDER BY Score DESC LIMIT 3,1; // Same query for 4th rank



SELECT * FROM <table name>
WHERE {comparisson}..
ORDER BY <column name>...
LIMIT <offset value>, <limit value>; //another way of writing
