```SQL
CREATE DATABASE club_members;

USE club_members;
```

### To view the table

```
SELECT * FROM club;
```
### Since an 'Id' column is missing we add an Id Column in the table......................

```
Alter Table club
Add Id Int Identity(1,1);
```

### The column contains some names in lower case and some in upper case.So, CAPITALISING first letter of full_name and updating it.

```
DECLARE @value VARCHAR(50)
SET @value = 'small'
SELECT UPPER(LEFT(@value, 1)) + SUBSTRING(@value, 2, LEN(@value));

SELECT full_name, UPPER(LEFT(full_name, 1)) + SUBSTRING(full_name, 2, LEN(full_name)) AS FullName
FROM club
;

UPDATE club SET full_name = UPPER(LEFT(full_name, 1)) + SUBSTRING(full_name, 2, LEN(full_name))
FROM club;

```

### Removing and Updating whitespaces in full_name column

```
UPDATE club
SET 
full_name = LTRIM(full_name);
```

### Removing special characters from column and updating it..........

```
UPDATE club
SET full_name = REPLACE(full_name,'???','')
WHERE full_name = full_name;
```
### Converting all upper case and lower case full_names to proper case/title case......

```
UPDATE club
 SET full_name = UPPER(LEFT(full_name,1)) + LOWER(RIGHT(full_name, LEN(full_name) - 1));
```

### In Age column some ages have three digit at the end............

```
UPDATE club
set age = 
	CASE
		WHEN LEN(age) = 0 THEN NULL
		WHEN LEN(age) = 3 THEN substring(age,1,2)	
		ELSE age
	END;
```
### Verifying if there are any 3 digit number in the Age column.....

```
SELECT age FROM club
WHERE age > 99;

SELECT age FROM club;
```

### Removing the whitespaces from maritital_status 

```
SELECT * FROM club;

UPDATE club
 SET maritial_status = 
 CASE 
		WHEN TRIM(maritial_status) = '' THEN NULL
		ELSE TRIM(maritial_status) 
		END;
```

### Capitalising the first character in maritial_status.....

```
DECLARE @value VARCHAR(50)
SET @value = 'small'
SELECT UPPER(LEFT(@value, 1)) + SUBSTRING(@value, 2, LEN(@value));
```
```
SELECT maritial_status, UPPER(LEFT(maritial_status, 1)) + SUBSTRING(maritial_status, 2, LEN(maritial_status)) AS MaritialStatus
FROM club
;
```
```
UPDATE club SET maritial_status = UPPER(LEFT(maritial_status, 1)) + SUBSTRING(maritial_status, 2, LEN(maritial_status))
FROM club;
```

### Trimming any whitespaces and converting the column into lowercases, since emails are case sensitive....

```
SELECT email FROM club;

UPDATE club
SET email = 
		TRIM(LOWER(email));
```
### Trimming the whitespaces from phone column...........

```
SELECT full_name,phone FROM club;

UPDATE club
SET phone = 
CASE 
		WHEN TRIM(phone) = '' THEN NULL
		ELSE TRIM(phone)
		END;
```
```
SELECT city
FROM club
WHERE city = '' ;
```
### Trimming the whitespaces from job title column......

```
UPDATE club
SET job_title = 
CASE 
		WHEN TRIM(job_title) = '' THEN NULL
		ELSE TRIM(job_title)
		END;

SELECT * FROM club;
```
### Some mebership_date are dated to 1921. We need convert that incoreect data to 2021.....

```
SELECT membership_date,full_name 
FROM club
WHERE membership_date < '1950-01-01';
```

```
UPDATE club
SET membership_date = DATEADD(year,100,membership_date)
WHERE membership_date < '1950-01-01';
```
```
SELECT membership_date FROM club;
```

### Some of the state names have been mispelled.Correcting those errors.........

```
UPDATE club
SET state = REPLACE(state,'South Dakotaaa','South Dakota');
```
```
SELECT * FROM club;
```
### Trimming whitespaces in the state column and updating empty cells to Null value......

```
UPDATE club
SET state = 
CASE 
		WHEN TRIM(state) = '' THEN NULL
		ELSE TRIM(state)
		END;
```
### Deleting the duplicate values...............

```
SELECT email,count(email)
FROM club
GROUP BY email
ORDER BY count(email) DESC;
```
```
DELETE FROM club 
WHERE Id Not In(
			Select Min(Id)
			from club
			Group by full_name, Age,email
			);
```
```
SELECT COUNT(email) FROM club;
```
