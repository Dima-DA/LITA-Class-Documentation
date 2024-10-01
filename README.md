# LITA-Class-Documentation
## Project Title: SQL Veiws
---
[Project Overview](#project-overview)

[Tools Used](#tools-used)

[Query used](#query-used)

### Project Overview
SQL views are virtual tables that simplify complex queries, gives you the flexibility to include only the details you want to share.
-  Customization: You can add and remove columns easily : just select the view created, right click, select design.
-  Visual Appeal: The connecting lines and dynamic movement are oddly satisfying.
-  User Friendly: Simply check and uncheck boxes to add or remove columns.
-  Easy creation: Just like pivot tables in Excel, its quite easy to create
(vemployee--- is the name of the view I want to create, you can name it anything, even Gloria)
-  security: Control access o sensitive data.
-  Performance: Optimize queries for faster retrieval. So, even if you lost your query you can retrieve it from the view, amazing right? No scrolling to number 33333 to get that code.
-  Consistency: Ensures everyone uses same logic for reporting.

### Tools Used
SQL [Download Here](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)
### Query used
```sql
CREATE VIEW vemployee AS
SELECT employee.staffid FROM employee```

vemployee- is the name of the view I want to create
employee.staffid is a column on employee table already created
```

## SQL 'CASE WHEN' statement.
---
### Overview

CASE WHEN is a conditional expression thats alllows you to create different output based on conditions. Comparing to excel, it is like VLOOKUP.
. CASE usually stands alone 
. WHEN is the condition.

### CASE WHEN Practise:
Goal:To categorise staff based on age. I want to see the Age and LastNames columns and create a new category to show staff cadre.
60 = senior Executive; 59-50 = Executive; 45 - 40 = Manager;39 - 20 = Assistant Manager.

*CODE*
Note: between 59 and 50, will retun an error, so, the higher value should always come last- Between 50 and 59 is the correct line.

````SQL
SELECT lastname, Age,
case
	when age >= 60 then 'senior executive'
	when age between 50 and 59 then 'Executive'
	when age between 40 and 45 then 'Manager'
	when age between 20 and 30 then 'Assistant Manager'
	else 'unknown'
	end as cadre_by_age from Salary ```

Practise 2: Update the state of origin using CASE WHEN.

```SQL
UPDATE Salary
	set state_of_origin=
case 
	when staffid= 'AB401' then 'oyo'
	when staffid ='AB212'then 'Ibadan'
	when staffid ='AB223' then 'ondo'
	when staffid ='AB234' then 'akwa'
	when staffid ='AB254'then 'lagos'
	when staffid = 'AB249'then 'akure'
	when staffid= 'AB298'then 'Edo'
	when staffid= 'AB260' then 'Imo'
else 'nothere'
end ```





