# DATA CLEANING USING SQL

For this project we will be cleaning the data of all the anomalies as a part of data analysis.Following will be the tasks that will be carried out as a part of **Data Cleaning** process.

1. Adding an **ID** column.
2. Removing whitespaces, special characters and Capitalizing the names in **full_name** column.
3. Removing the last two digits from **Age** column.
4. Capitalizing and correcting the spellings in **Maritial_status** column.
5. Deleting duplicate emails from **email** column.
6. Updating the **Membership_date** column.
7. Checking for empty columns.

Let's take a look at the data:-

 'code()'
 SELECT * FROM club 
 LIMIT 15;
