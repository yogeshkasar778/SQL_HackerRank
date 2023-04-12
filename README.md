# SQL HackerRank Question Practice -

![sql-illustration](https://user-images.githubusercontent.com/118357991/231157432-121cbac9-92e4-472f-a75a-aeff422b10e7.png)

### BASIC SELECT - 
#### Q1.Query all columns (attributes) for every row in the CITY table.
The CITY table is described as follows:

![1449729804-f21d187d0f-CITY](https://user-images.githubusercontent.com/118357991/231157971-6a250971-3ad9-4afd-9d36-799150a3f0ef.jpg)

   My Solution (MySQL):
   
       SELECT * FROM CITY;
     
#### Q2.Query all columns for a city in CITY with the ID 1661.

   My Solution (MySQL):
   
       SELECT * FROM CITY WHERE ID =1661;

#### Q3.Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

   My Solution (MySQL):
   
       SELECT * FROM CITY WHERE COUNTRYCODE = 'JPN';

#### Q4.Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.

   My Solution (MySQL):
   
       SELECT NAME FROM CITY WHERE COUNTRYCODE = 'JPN';

#### Q5.Query the names of all the American cities in the CITY table. The COUNTRYCODE for Japan is USA.

   My Solution (MySQL):
   
       SELECT NAME FROM CITY WHERE COUNTRYCODE = 'USA';
     
#### Q6.Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

   My Solution (MySQL):
   
       SELECT * FROM CITY WHERE POPULATION > 100000 AND COUNTRYCODE = 'USA';
     
#### Q7.Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

   My Solution (MySQL):
   
       SELECT NAME FROM CITY WHERE POPULATION > 120000 AND COUNTRYCODE = 'USA';    
     
#### Q8.Query a list of CITY and STATE from the STATION table.

The **STATION** table is described as follows:

![1449345840-5f0a551030-Station](https://user-images.githubusercontent.com/118357991/231164045-963988cb-b80d-40f9-8a1a-45d275a0499d.jpg)

   My Solution (MySQL):
   
       SELECT CITY, STATE FROM STATION;     
     
#### Q9.Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

   My Solution (MySQL):
  
       SELECT DISTINCT CITY FROM STATION WHERE MOD(ID, 2) = 0;     
     
#### Q10.Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

   My Solution (MySQL):
  
       SELECT  COUNT(CITY) - COUNT(DISTINCT(CITY)) FROM STATION;  
       
#### Q11.Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

   My Solution (MySQL):
  
       SELECT  CITY, LENGTH(CITY) FROM STATION WHERE LENGTH(CITY) = (SELECT MIN(LENGTH(CITY)) FROM STATION) 
       OR LENGTH(CITY) = (SELECT MIN(LENGTH(CITY)) FROM STATION)
       ORDER BY LENGTH(CITY) DESC, CITY ASC LIMIT 2;    
     
#### Q12.Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

   My Solution (MySQL):
  
       SELECT  DISTINCT CITY FROM STATION
       WHERE CITY REGEXP '^[A,E,I,O,U]';     
     
#### Q13.Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

   My Solution (MySQL):
  
       SELECT  DISTINCT CITY FROM STATION
       WHERE CITY REGEXP '[A,E,I,O,U]$';          
     
#### Q14.Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

   My Solution (MySQL):
  
       SELECT  DISTINCT CITY FROM STATION
       WHERE CITY REGEXP '^[A,E,I,O,U].*[A,E,I,O,U]$';      

#### Q15.Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

   My Solution (MySQL):
  
       SELECT  DISTINCT CITY FROM STATION
       WHERE CITY NOT REGEXP '^[A,E,I,O,U]';  

#### Q16.Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

   My Solution (MySQL):
  
       SELECT  DISTINCT CITY FROM STATION
       WHERE CITY NOT REGEXP '^[A,E,I,O,U].*[A,E,I,O,U]$'; 

#### Q17.Query the list of CITY names from STATION that either do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

   My Solution (MySQL):
  
       SELECT  DISTINCT CITY FROM STATION
       WHERE CITY  REGEXP '^[^A,E,I,O,U]' AND REGEXP '[^A,E,I,O,U]$';
      
#### Q18.Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

The STUDENTS table is described as follows:

![1443815209-cf4b260993-2](https://user-images.githubusercontent.com/118357991/231522914-2e95d980-50eb-4a0b-876f-8720394349a4.png)

   My Solution (MySQL):
  
       SELECT  NAME FROM STUDENTS
       WHERE MARKS > 75
       ORDER BY RIGHT(NAME,3), ID;
       
#### Q19.Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

The Employee table containing employee data for a company is described as follows:

![1458558202-9a8721e44b-ScreenShot2016-03-21at4 32 59PM](https://user-images.githubusercontent.com/118357991/231523874-a418d84f-2747-4982-91d5-6cd69f98680e.png)

   My Solution (MySQL):
  
       SELECT  name FROM Employee
       ORDER BY name ASC;

#### Q20.Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.

   My Solution (MySQL):
   
         SELECT name FROM Employee
         WHERE salary > 2000 AND months < 10
         ORDER BY employee_id ASC;
   





