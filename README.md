## Crowdfunding ETL

### Project Overview
This project involved building an ETL pipeline using Python, Pandas, and either Python dictionary methods or regular expressions to extract and transform data. The goal was to create four CSV files and use the CSV file data to create an ERD and a table schema. Finally, the CSV file data was uploaded into a Postgres database.

### Technologies Used
- Python
- Pandas
- Regular Expressions
- PostgreSQL

### Methodology
The following steps were taken to complete the project:

1. Created the Category and Subcategory DataFrames: Extracted and transformed the crowdfunding.xlsx Excel data to create a category DataFrame with a "category_id" column that had entries going sequentially from "cat1" to "catn" and a "category" column that contained only the category titles. Similarly, a subcategory DataFrame was created with a "subcategory_id" column that had entries going sequentially from "subcat1" to "subcatn" and a "subcategory" column that contained only the subcategory titles. Exported the category DataFrame as category.csv and the subcategory DataFrame as subcategory.csv.

2. Created the Campaign DataFrame: Extracted and transformed the crowdfunding.xlsx Excel data to create a campaign DataFrame with the following columns:
  - cf_id
  - contact_id
  - company_name
  - blurb column, renamed to "description"
  - goal column, converted to float data type
  - pledged column, converted to float data type
  - outcome column
  - backers_count column
  - country column
  - currency column
  - launched_at column, renamed to "launch_date" and with the UTC times converted to the datetime format
  - deadline column, renamed to "end_date" and with the UTC times converted to the datetime format
  - category_id column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
  - subcategory_id column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame. Exported the campaign DataFrame as campaign.csv.

3. Created the Contacts DataFrame: Extracted and transformed the data from the contacts.xlsx Excel file using Python dictionary methods. Imported the contacts.xlsx file into a DataFrame, iterated through the DataFrame, converting each tuple to a dictionary, created a new DataFrame that contained the extracted data, split each "name" column value into a first and last name, and placed each in a new column. Cleaned and exported the DataFrame as contacts.csv and saved it to GitHub.

4. Created the Crowdfunding Database: Sketched an ERD of the tables by inspecting the four CSV files and used the information from the ERD to create a table schema for each CSV file. Specified the data types, primary keys, foreign keys, and other constraints and saved the database schema as a Postgres file named crowdfunding_db_schema.sql. Created a new Postgres database and uploaded each of the saved dataframe csvs to the new crowdfunding_db. SQL SELECT statements verified the data integrity.

Author: Lacey Morgan

Note: Erica Graboyes also worked on this project with her own code, which is available on her GitHub.
