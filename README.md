CREATE TABLE EMPLOYEEDETAILS
(EMPLOYEEID INT,
 EMPLOYEE_NAME VARCHAR(50),
 EMPLOYEE_GENDER VARCHAR(20),
 EMPLOYEE_AGE INT,
 EMPLOYEE_COUNTRY VARCHAR(50)
 ); 
 INSERT INTO EMPLOYEEDETAILS VALUES
 (11001,'RAVI KUMAR', 'MALE',26,'INDIA'),
 (11002,'RAJU KUMAR','MALE',28,'INDIA'),
 (11003,'SUMITH S','MALE',32,'INDIA'),
 (11004,'MUNNA DAS','MALE',35,'INDIA'),
 (11005,'DEVI KUMARI','FEMALE',29,'INDIA'),
 (11006,'BARR FAUGHNY','FEMALE', 33,'LONDON'),
 (11007,'RAM MAHESH','MALE',29,'INDIA'),
 (11008,'RAMA P','MALE',22,'USA'),
 (11009,'NEHA M','FEMALE',31,'UK'),
 (11010,'JANNAT JAMES','FEMALE',29,'LONDON');
CREATE TABLE EMPLOYEE_SALARY
(EMPLOYEEID INT,
 EMPLOYEE_DEPT VARCHAR(60),
 EMPLOYEE_DATE_OF_JOINING DATE,
 EMPLOYEE_SALARY INT
 );
 INSERT INTO EMPLOYEE_SALARY VALUES
 (11001,'WEBSITE','2022-12-02',25000),
 (11002,'ENGINEER','2022-03-04',27000),
 (11003,'DEVELOPER','2021-02-08',30000),
 (11004,'DATA ANALYST','2021-03-02',32000),
 (11005,'ANALYST','2022-04-02',29000),
 (11006,'BI ANALYST','2023-01-01',35000),
 (11007,'POWER BI DEVELOPER','2022-08-07',42000),
 (11008,'DATA SCIENTIST','2021-06-03',44000),
 (11009,'POWER BI ADMIN','2022-12-25',62000),
 (11010,'DATA ANALYTICS','2021-09-02',52000);
SELECT * FROM EMPLOYEEDETAILS;
SELECT * FROM EMPLOYEE_SALARY;
SELECT EMPLOYEEID,
       EMPLOYEE_NAME,
       EMPLOYEE_GENDER,
       EMPLOYEE_AGE,
       EMPLOYEE_COUNTRY
FROM EMPLOYEEDETAILS;
SELECT EMPLOYEEID,
      EMPLOYEE_DEPT,
      EMPLOYEE_DATE_OF_JOINING,
      EMPLOYEE_SALARY
FROM EMPLOYEE_SALARY;
SELECT DISTINCT(EMPLOYEE_NAME) FROM EMPLOYEEDETAILS;
SELECT DISTINCT(EMPLOYEE_DEPT) FROM EMPLOYEE_SALARY;
SELECT DISTINCT(EMPLOYEE_COUNTRY) FROM EMPLOYEEDETAILS;
SELECT COUNT(EMPLOYEE_NAME) FROM EMPLOYEEDETAILS;
SELECT COUNT(EMPLOYEE_DEPT) FROM EMPLOYEE_SALARY;
SELECT SUM(EMPLOYEE_SALARY) AS TOTAL_SALARY FROM EMPLOYEE_SALARY;
SELECT AVG(EMPLOYEE_SALARY) AS AVG_SALARY FROM EMPLOYEE_SALARY;
SELECT MAX(EMPLOYEE_SALARY) AS MAX_SALARY FROM EMPLOYEE_SALARY;
SELECT MIN(EMPLOYEE_SALARY) AS MIN_SALARY FROM EMPLOYEE_SALARY;
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_NAME='SUMITH S';
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_NAME IN('RAMA P','DEVI KUMARI');
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_COUNTRY='INDIA'
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_COUNTRY='UK';
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_COUNTRY IN ('LONDON','USA');
SELECT * FROM EMPLOYEE_SALARY 
WHERE EMPLOYEEID=11005;
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEEID IN ('11005','11006','11010');
SELECT * FROM EMPLOYEE_SALARY 
WHERE EMPLOYEE_DEPT='ENGINEER';
SELECT * FROM EMPLOYEE_SALARY 
WHERE EMPLOYEE_DEPT='DATA ANALYST';
SELECT * FROM EMPLOYEE_SALARY 
WHERE EMPLOYEE_DEPT IN ('DEVELOPER','DATA ANALYTICS','POWER BI ADMIN');
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_AGE<25;
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_AGE<=25;
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_AGE>=25;
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_AGE>30;
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_AGE<>30;
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_AGE<25 AND EMPLOYEE_GENDER='MALE';
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_AGE>30 AND EMPLOYEE_GENDER IN ('MALE','FEMALE');
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_AGE<>28 AND EMPLOYEE_GENDER IN ('MALE','FEMALE');
SELECT * FROM EMPLOYEE_SALARY 
WHERE EMPLOYEE_DATE_OF_JOINING='2022-12-01';
SELECT * FROM EMPLOYEE_SALARY 
WHERE EMPLOYEE_SALARY>25000;
SELECT * FROM EMPLOYEE_SALARY 
WHERE EMPLOYEE_SALARY>25000 AND EMPLOYEE_DEPT='DEVELOPER';
SELECT * FROM EMPLOYEE_SALARY 
WHERE EMPLOYEE_SALARY>=25000 AND EMPLOYEE_DEPT IN ('POWER BI DEVELOPER','ENGINEER','DEVELOPER');
SELECT * FROM EMPLOYEE_SALARY 
WHERE EMPLOYEE_SALARY<=30000 AND EMPLOYEE_DEPT IN ('POWER BI DEVELOPER','ENGINEER','DEVELOPER');
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_NAME LIKE 'S%';
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_NAME LIKE '%A%';
SELECT * FROM EMPLOYEEDETAILS 
WHERE EMPLOYEE_NAME LIKE '%U';
SELECTEMPLOYEE_GENDER,COUNT(*) AS GEN FROM EMPLOYEE DETAILS
GROUP BY EMPLOYEE_GENDER;
SELECT EMPLOYEE_DEPT, COUNT(*) AS DEPT  FROM EMPLOYEE_SALARY
GROUP BY EMPLOYEE_DEPT;
SELECT EMPLOYEE_DEPT, COUNT(*) AS DEPT FROM EMPLOYEE_SALARY
WHERE EMPLOYEE_SALARY>=32000
GROUP BY EMPLOYEE_DEPT
ORDER BY DEPT;
SELECT * FROM EMPLOYEEDETAILS
ORDER BY EMPLOYEE_NAME;
SELECT * FROM EMPLOYEEDETAILS
ORDER BY EMPLOYEE_NAME DESC;
SELECT EMPLOYEE_NAME, COUNT(EMPLOYEE_NAME) AS "FULL NAME" FROM EMPLOYEEDETAILS
WHERE EMPLOYEE_AGE>25
GROUP BY EMPLOYEE_NAME
ORDER BY 'FULL NAME';
SELECT * FROM EMPLOYEEDETAILS;
SELECT * FROM EMPLOYEE_SALARY;
INSERT INTO EMPLOYEESALARY VALUES
(11011,'ENGINEER','2022-12-29',24000),
(NULL,'POWER BI','2022-12-28',26000),
(11013,'DATA ANALYST','2022-12-31',22000);
INSERT INTO EMPLOYEEDETAILS VALUES
(11011,'MAHI S','FEMALE',25,'INDIA'),
(11012,'NULL','NULL',25,'CHINA')
(NULL,'SURESH A','MALE',NULL,'LONDON');
SELECT * FROM EMPLOYEEDETAILS 
JOIN EMPLOYEE_SALARY 
ON EMPLOYEEDETAILS.EMPLOYEEID=EMPLOYEE_SALARY.EMPLOYEEID;
SELECT * FROM EMPLOYEEDETAILS A
JOIN EMPLOYEE_SALARY B
ON A.EMPLOYEEID=B.EMPLOYEEID;
SELECT EMPLOYEE_NAME,
      EMPLOYEE_GENDER,
      EMPLOYEE_DEPT,
      EMPLOYEE_SALARY
FROM EMPLOYEEDETAILS A
JOIN EMPLOYEE_SALARY B
ON A.EMPLOYEEID=B.EMPLOYEEID;
SELECT EMPLOYEE_NAME, 
       EMPLOYEE_GENDER,
       EMPLOYEE_DEPT,
       EMPLOYEE_SALARY
FROM EMPLOYEEDETAILS A
LEFT JOIN EMPLOYEE_SALARY B
ON A.EMPLOYEEID=B.EMPLOYEEID;
SELECT EMPLOYEE_NAME, 
       EMPLOYEE_GENDER,
       EMPLOYEE_DEPT,
       EMPLOYEE_SALARY
FROM EMPLOYEEDETAILS A
RIGHT JOIN EMPLOYEE_SALARY B
ON A.EMPLOYEEID=B.EMPLOYEEID;
SELECT EMPLOYEE_NAME,
       EMPLOYEE_GENDER,
       EMPLOYEE_DEPT,
       EMPLOYEE_SALARY
FROM EMPLOYEEDETAILS A
FULL OUTER JOIN EMPLOYEE_SALARY B
ON A.EMPLOYEEID=B.EMPLOYEEID;
SELECT EMPLOYEE_DEPT, EMPLOYEEE_SALARY,
CASE
    WHEN EMPLOYEE_DEPT IN('DEVELOPER','DATA ANALYST')THEN 'IT'
    ELSE 'NON IT'
    END AS 'SERVICES'
FROM EMPLOYEE_SALARY;
SELECT EMPLOYEE_NAME,EMPLOYEE_GENDER,EMPLOYEE_COUNTRY,
CASE
   WHEN EMPLOYEE_COUNTRY IN('INDIA') THEN 'INDIAN'
      ELSE 'NON INDIAN'
      END AS 'CITIZENSHIP'
FROM EMPLOYEEDETAILS;
SELECT EMPLOYEE_NAME, 
       EMPLOYEE_DEPT,
       SUM(EMPLOYEE_SALARY) AS 'TOTAL SALARY'
FROM EMPLOYEE_SALARY
JOIN EMPLOYEEDETAILS 
ON EMPLOYEE_SALARY.EMPLOYEEID=EMPLOYEEDETAILS.EMPLOYEEID
GROUP BY EMPLOYEE_NAME,EMPLOYEE_DEPT;
SELECT EMPLOYEE_NAME, 
       EMPLOYEE_DEPT,
       AVG(EMPLOYEE_SALARY) AS 'AVG SALARY'
FROM EMPLOYEE_SALARY
JOIN EMPLOYEEDETAILS 
ON EMPLOYEE_SALARY.EMPLOYEEID=EMPLOYEEDETAILS.EMPLOYEEID
GROUP BY EMPLOYEE_NAME,EMPLOYEE_DEPT;
WITH CTE_EMPLOYEE AS 
(SELECT FIRSTNAME,LASTNAME,GENDER,SALARY,
COUNT(GENDER) OVER (PARTITION BY GENDER) AS TOTALGENDER,
AVG(SALARY) OVER (PARTITION BY SALARY) AS AVGSALARY
FROM EMPLOYEEDETAILS A
JOIN EMPLOYEE_SALARY B
ON A.EMPLOYEEID=B.EMPLOYEEID
WHERE EMPLOYEE_SALARY>25000
)
SELECT * FROM CTE_EMPLOYEE;
WITH CTE_EMPLOYEE AS 
(SELECT EMPLOYEE_NAME, EMPLOYEE_GENDER, EMPLOYEE_COUNTRY,EMPLOYEE_DEPT,EMPLOYEE_SALARY,
COUNT(EMPLOYEE_GENDER) OVER (PARTITION BY EMPLOYEE_GENDER) AS TOTALGENDER
MIN(EMPLOYEE_SALARY) OVER (PARTITION BY EMPLOYEE_SALARY) AS MINSALARY
FROM EMPLOYEEDETAILS A
JOIN EMPLOYEE_SALARY B
ON A.EMPLOYEEID=B.EMPLOYEEID
)
SELECT * FROM CTE_EMPLOYEE;





































































