## 1. How many participants are in the dataset?


SELECT COUNT(DISTINCT User_ID) AS Total_participants
FROM sm


## 2. What is the average daily phone usage for each occupation?

SELECT Occupation, AVG(Daily_Phone_Hours) AS Average_Daily_phone_usage
FROM sm
GROUP BY Occupation
ORDER BY Average_Daily_phone_usage DESC


## 3. Which gender has the highest average work productivity score?


SELECT Gender, AVG(Work_Productivity_Score) AS Average_productivity
FROM sm
GROUP BY Gender
ORDER BY Average_productivity DESC


## 4. How many users use each device type?

SELECT Device_Type, COUNT(User_ID) AS Total_users
FROM sm
GROUP BY Device_Type
ORDER BY Total_users DESC


## 5. What is the overall average daily phone usage?


SELECT AVG(Daily_Phone_Hours) AS Average_Daily_phone_usage
FROM sm


## 6. What is the average daily phone usage of Business Owners?


SELECT AVG(Daily_Phone_Hours) AS Business_Owners_Average_Daily_phone_usage
FROM sm
WHERE Occupation = 'Business Owner'


## 7. Who are the top 5 users with the highest daily phone usage?

SELECT TOP 5
    User_ID,
    Occupation,
    Daily_Phone_Hours
FROM sm
ORDER BY Daily_Phone_Hours DESC


## 8. What are the average sleep hours of users who consume four or fewer cups of caffeine?


SELECT
    User_ID,
    Caffeine_Intake_Cups,
    Occupation,
    AVG(Sleep_Hours) AS Average_sleep_hours
FROM sm
WHERE Caffeine_Intake_Cups <= 4
GROUP BY
    Occupation,
    Caffeine_Intake_Cups,
    User_ID
ORDER BY Occupation DESC


## 9. What is the total and average caffeine intake for each occupation?

SELECT
    Occupation,
    SUM(Caffeine_Intake_Cups) AS Total_Caffeine,
    AVG(Caffeine_Intake_Cups) AS Avg_Caffeine
FROM sm
GROUP BY Occupation
ORDER BY Total_Caffeine DESC


## 10. Which occupations have an average stress level of 5?


SELECT
    Occupation,
    AVG(Stress_Level) AS avg_stress,
    AVG(Work_Productivity_Score) AS Avg_Prodcutivity,
    SUM(Caffeine_Intake_Cups) AS Total_Caffeine
FROM sm
GROUP BY Occupation
HAVING AVG(Stress_Level) = 5
ORDER BY Total_Caffeine DESC


## 11. Which occupations have more than 12,500 users?

SELECT
    Occupation,
    COUNT(*) AS Total_Users
FROM sm
GROUP BY Occupation
HAVING COUNT(*) > 12500
ORDER BY Occupation DESC


## 12. What is the average caffeine intake by gender?

SELECT
    Gender,
    AVG(Caffeine_Intake_Cups) AS Avg_Caffeine_Intake
FROM sm
GROUP BY Gender
ORDER BY Avg_Caffeine_Intake DESC


## 13. Which users have above-average daily phone usage?

SELECT
    User_ID,
    Occupation,
    Daily_Phone_Hours
FROM sm
WHERE Daily_Phone_Hours > (
    SELECT AVG(Daily_Phone_Hours)
    FROM sm
)
ORDER BY Daily_Phone_Hours DESC


## 14. How are users grouped into age categories?


SELECT
    User_ID,
    Age,
    CASE
        WHEN Age BETWEEN 0 AND 18 THEN '0-18'
        WHEN Age BETWEEN 19 AND 35 THEN '19-35'
        WHEN Age BETWEEN 36 AND 45 THEN '36-45'
        WHEN Age BETWEEN 46 AND 55 THEN '46-55'
        ELSE '56+'
    END AS Age_group
FROM sm
ORDER BY Daily_Phone_Hours

