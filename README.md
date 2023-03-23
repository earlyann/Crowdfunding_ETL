# Crowdfunding ETL

## Project Overview
In this project, I built an ETL pipeline using Python, Pandas, and either Python dictionary methods or regular expressions to extract and transform data. The goal was to create four CSV files and use the CSV file data to create an ERD and a table schema. Finally, I uploaded the CSV file data into a Postgres database.

### Technologies Used
 - Python
 - Pandas
 - Regular Expressions
 - PostgreSQL
 
### Methodology
I followed the below steps to complete this project:

1. Created the Category and Subcategory DataFrames: I extracted and transformed the crowdfunding.xlsx Excel data to create a category DataFrame that had a "category_id" column that had entries going sequentially from "cat1" to "catn", where n is the number of unique categories, and a "category" column that contained only the category titles. We also extracted and transformed the crowdfunding.xlsx Excel data to create a subcategory DataFrame that had a "subcategory_id" column that had entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories, and a "subcategory" column that contained only the subcategory titles. We then exported the category DataFrame as category.csv and the subcategory DataFrame as subcategory.csv and saved them to our GitHub repository.

2. Created the Campaign DataFrame: I extracted and transformed the crowdfunding.xlsx Excel data to create a campaign DataFrame that had the following columns:

- The "cf_id" column
- The "contact_id" column
- The "company_name" column
- The "blurb" column, renamed to "description"
- The "goal" column, converted to the float data type
- The "pledged" column, converted to the float data type
- The "outcome" column
- The "backers_count" column
- The "country" column
- The "currency" column
- The "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime  format
- The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime      format
- The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
- The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame
- I then exported the campaign DataFrame as campaign.csv

Create the Contacts DataFrame: I extracted and transformed the data from the contacts.xlsx Excel file. We chose to use Python dictionary methods and completed the following steps:

- Imported the contacts.xlsx file into a DataFrame.
- Iterated through the DataFrame, converting each tuple to a dictionary.
- Created a new DataFrame that contained the extracted data.
- Split each "name" column value into a first and last name, and placed each in a new column.
- Cleaned and exported the DataFrame as contacts.csv and saved it to GitHub.
- Create the Crowdfunding Database: We sketched an ERD of the tables by inspecting the four CSV files and used the information from the ERD to create a table schema for each CSV file. I specified the data types, primary keys, foreign keys, and other constraints and saved the database schema as a Postgres file named crowdfunding_db_schema.sql. I then created a new Postgres database and uploaded each of the saved dataframe csvs to the new crowdfunding_db. SQL SELECT statements verify the data integreity. 

Author: Lacey Morgan
