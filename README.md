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
     
     
     
     
     
     
     
     
