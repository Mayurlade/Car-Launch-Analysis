# Car-Launch-Analysis
Project is created to launch a new car in UK market on the basis of car sales history. To launch car need to think about some specifications like car brand , car price, engine size, fuel type and transmission type . So that most of the people can buy the car and sales will go on and on and on.
## Snapshot of final dashboard created with excel
![Screenshot (578)](https://user-images.githubusercontent.com/118553136/210787169-c4fd6bde-b8ec-4591-957f-47c450703c09.png)

## Project Analysis
[To see project ,analysis , findings and SQL Code just click here](https://1drv.ms/u/s!Asc9JcyLXumPbGVlzK9HzP7IfxA?e=HuJjmt)

## SQL Codes

------->>>>>>>>>>>>>>>>>>>>>>>>INCOME CLASSES IN UK BASED ON THE PRICE OF CAR

WITH CTE AS(
SELECT *,
CASE
WHEN PRICE < 33000 THEN 'LOWER_INCOME_CLASS'
WHEN PRICE BETWEEN 33000 AND 70000 THEN 'MIDDLE_INCOME_CLASS'
WHEN PRICE > 70000 THEN 'UPPER_INCOME_CLASS'
END AS INCOME_CLASS
FROM AUDI 
)
SELECT INCOME_CLASS,COUNT(INCOME_CLASS) OVER (PARTITION BY INCOME_CLASS) COUNT_ FROM CTE
