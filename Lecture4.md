SELECT <column name> 
AS <alias name>
FROM <table name> ;

Sample command - 
SELECT DOB AS "Date of Birth" FROM students2;


SELECT CONCAT ( <Column 1>,<Column 2>) 
AS <alias name>
FROM <table name>;

Sample Command -
SELECT CONCAT (Name,Section) AS Info FROM students2;
SELECT CONCAT (Name,' ',Section) AS Info FROM students2;  // add a space
SELECT CONCAT (Name,' ',Section,' ', Score) AS Info FROM students2; // multiple columns
SELECT CONCAT (Name,' ',Section,' ', Score) AS Info FROM students2 ORDER BY Info;




SELECT * FROM <table name> 
AS <alias name>;


Sample Command -

SELECT * FROM students2 AS kids;
SELECT * FROM students2 AS kids WHERE kids.Marital_status = "Single" AND kids.Score >80;

 SELECT t2.Name,t2.Score  FROM students2 AS t1, students2 AS t2 WHERE t1.DOB = t2.DOB AND t1.Name != t2.Name; // Self Join





SELECT DISTINCT <Column name>
FROM <table name>;


Sample Command -
SELECT DISTINCT Name FROM students2;
SELECT DISTINCT DOB FROM students2;


SELECT DISTINCT <column name1>, <column name2>...
FROM <table name>;

Sample Command -
SELECT DISTINCT DOB, Score  FROM students2;




SELECT COUNT(<column name>) 
FROM <table name>;

Sample Command -
SELECT COUNT(*) FROM students2;
SELECT COUNT(*) AS "Count of Students" FROM students2;

SELECT COUNT(*) FROM students2 WHERE Score >70 ;

