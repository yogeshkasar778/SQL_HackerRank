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

### Advanced SELECT - 

#### Q21.Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

     - Equilateral: It's a triangle with 3 sides of equal length.
     - Isosceles: It's a triangle with 2 sides of equal length.
     - Scalene: It's a triangle with 3 sides of differing lengths.
     - Not A Triangle: The given values of A, B, and C don't form a triangle.

The TRIANGLES table is described as follows:

![1443815629-ac2a843fb7-1](https://user-images.githubusercontent.com/118357991/231813836-488eb083-2ec1-422c-9643-1e05ae1fdf26.png)

Each row in the table denotes the lengths of each of a triangle's three sides.

Sample Input

![1443815827-cbfc1ca12b-2](https://user-images.githubusercontent.com/118357991/231813983-244a45b9-9136-4d02-80b3-decd09cce415.png)

   My Solution (MySQL):
  
       SELECT 
             CASE
               WHEN A + B <= C OR A + C <= B OR B + C <= A THEN 'Not A Triangle'
               WHEN A = B AND B = C THEN 'Equilateral'
               WHEN A = B OR B = C OR C = A THEN 'Isosceles'
             END AS triangle_type
        FROM TRIANGLES;
       
#### Q22.Amber's conglomerate corporation just acquired some new companies. Each of the companies follows this hierarchy:

![1458531031-249df3ae87-ScreenShot2016-03-21at8 59 56AM](https://user-images.githubusercontent.com/118357991/231822722-62175aa0-9fe5-4f0c-9164-cb51fdb952ca.png)

Given the table schemas below, write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.

Note:

- The tables may contain duplicate records.
- The company_code is string, so the sorting should not be numeric. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes  will be C_1, C_10, and C_2.

The following tables contain company data:

- Company: The company_code is the code of the company and founder is the founder of the company.

![1458535049-2a207c44b3-ScreenShot2016-03-21at8 50 52AM](https://user-images.githubusercontent.com/118357991/231823215-d5f596cc-5cc2-474d-ba35-90f810865895.png)

- Lead_Manager: The lead_manager_code is the code of the lead manager, and the company_code is the code of the working company.

![1458535073-919107f639-ScreenShot2016-03-21at8 51 03AM](https://user-images.githubusercontent.com/118357991/231823549-b5568e45-c5df-4eeb-99f5-81366cad1cea.png)

- Senior_Manager: The senior_manager_code is the code of the senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.

![1458535111-b1c48335b3-ScreenShot2016-03-21at8 51 15AM](https://user-images.githubusercontent.com/118357991/231823661-d855cb5b-45c1-4ce4-81f1-9232d18f5fb7.png)

- Manager: The manager_code is the code of the manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.

![1458535122-888f4bf340-ScreenShot2016-03-21at8 51 26AM](https://user-images.githubusercontent.com/118357991/231823814-8c1996eb-50d1-4639-8d62-6a740f0d7328.png)

- Employee: The employee_code is the code of the employee, the manager_code is the code of its manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.

![1458535134-878767e0d9-ScreenShot2016-03-21at8 51 52AM](https://user-images.githubusercontent.com/118357991/231823908-63f40e7f-e74d-49a9-a975-a423187ce534.png)


   My Solution (MySQL):
  
       SELECT C.company_code, C.founder,
              COUNT(DISTINCT E.lead_manager_code),
              COUNT(DISTINCT E.senior_manager_code),
              COUNT(DISTINCT E.manager_code),
              COUNT(DISTINCT E.employee_code)
       FROM Company C
       INNER JOIN Employee E
       ON C.company_code = E.company_code
       GROUP BY C.company_code, C.founder
       ORDER BY C.company_code;

#### Q23.Pivot the Occupation column in OCCUPATIONS so that each Name is sorted alphabetically and displayed underneath its corresponding Occupation. The output column headers should be Doctor, Professor, Singer, and Actor, respectively.

The OCCUPATIONS table is described as follows:

Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

![1443817648-1b2b8add45-2](https://user-images.githubusercontent.com/118357991/231827790-3abd211f-50bc-4819-8aaa-af71ac0abab9.png)

   My Solution (MySQL):
  
       WITH CTE AS(SELECT name,occupation,ROW_NUMBER() OVER (PARTITION BY Occupation ORDER BY Name) as R1 FROM OCCUPATIONS)
       SELECT MAX(CASE WHEN Occupation  = "Doctor" THEN Name END) AS Doctor,
              MAX(CASE WHEN Occupation  = "Professor" THEN Name END) AS Professor,
              MAX(CASE WHEN Occupation  = "Singer" THEN Name END) AS Singer,
              MAX(CASE WHEN Occupation  = "Actor" THEN Name END) AS Actor
       FROM CTE
       GROUP BY R1;


#### Q23.Generate the following two result sets: 
1.Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).

2.Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:
There are a total of [occupation_count] [occupation]s.
where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.

Note: There will be at least two entries in the table for each type of occupation.

![1443817648-1b2b8add45-2](https://user-images.githubusercontent.com/118357991/231827790-3abd211f-50bc-4819-8aaa-af71ac0abab9.png)

   My Solution (MySQL):
  
       (select concat(name,'(',left(occupation,1),')') 
       from occupations 
       order by name limit 100) 
       union
       ( SELECT CONCAT("There are a total of ",count(*)," ",lower(occupation),"s.") 
       FROM OCCUPATIONS group by(occupation) order by count(occupation),occupation limit 100);
