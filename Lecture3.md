
DELETE FROM <table name>
WHERE {comparisson}..
ORDER BY <column name>..
LIMIT <value>;

Sample command -
DELETE FROM students2  ORDER BY DOB LIMIT 1;
DELETE FROM students2  WHERE Score = 50 LIMIT 1;
DELETE FROM students2  WHERE Score = 50 ;


DELETE FROM <table name>;

Sample command -
DELETE FROM students; // To delete all the rows from the table





UPDATE <table name>
SET <coulmn name> = <value>, <column name> = <value>...
WHERE {condition}...;


Sample Command -
 UPDATE students2
    -> SET Name = "JD", Score = 100
    -> WHERE ID = 7;


UPDATE students2 SET Name = "Rohan",MaritalStatus = "Single" WHERE Name = "Sam Jain";
UPDATE Students2 SET MaritalStatus = "Married" WHERE Score< 70;
UPDATE students2 SET Score = 100;




ALTER TABLE <table name>
CHANGE <old Column name> <new column name> <data type> <meta info> ;

Sample Command - 

ALTER TABLE students2 CHANGE MaritalStatus Marital_Status enum('Married','Single','NA');

ALTER TABLE students2 CHANGE Name Name VARCHAR(50);


ALTER TABLE <table name> 
MODIFY <column name> {New meta/Paramaters};



Sample Command -

ALTER TABLE students2 MODIFY Name VARCHAR(40);
ALTER TABLE students2 MODIFY Name VARCHAR(40) DEFAULT "Not Known";
ALTER TABLE students2 MODIFY Name VARCHAR(40) DEFAULT "Not Known" NOT NULL;

ALTER TABLE students2 MODIFY Name INT(10);   // Error when not correct data type






ALTER TABLE <table name> 
ADD <new column name> <data type> ..{constraints if any};

Sample command -
ALTER TABLE students2 ADD Class int(2) ;



ALTER TABLE <table name>
ADD <new column name> <data type> FIRST; // add as first column

Sample Command -
ALTER TABLE students2 ADD Roll_No int(10) FIRST;



ALTER TABLE <table name>
ADD <new column name> <data type> AFTER <column name>; 
// Add column after a specific column 

Sample Command-
ALTER TABLE students2 ADD Mobile int(10) DEFAULT 0 AFTER Score ;




ALTER TABLE <table name>
DROP <column name>;

Sample Command-

 ALTER TABLE students2 DROP Roll_No;

 ALTER TABLE students2 DROP Mobile, ADD Section VARCHAR(5) DEFAULT "A" ;
 // Add and delete columns simultaneously 


 
