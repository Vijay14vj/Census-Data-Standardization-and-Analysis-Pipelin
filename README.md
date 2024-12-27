Project Name: Census Data Analysis and Integration

This project demonstrates how to clean, process, and analyze Census 2011 data for India. The project involves reading a CSV dataset, cleaning and transforming it, storing it in MongoDB, transferring it to MySQL, and enabling query execution using Streamlit.

-------Project Workflow---------

1. Load Raw Data
The project begins by loading the raw Census data stored in a CSV file.
The CSV file is processed, and any missing or erroneous data is cleaned.

2. Data Transformation
The columns in the raw CSV file are renamed according to a mapping provided in a JSON configuration file.
Specific transformations are applied to certain fields (e.g., state names are capitalized, and district names for Telangana and Ladakh are corrected).

3. Store Data in MongoDB
The cleaned data is then stored in MongoDB, a NoSQL database, for scalability and flexibility.
MongoDB helps in handling large datasets and makes it easy to retrieve data for further processing.

4. Transfer Data to MySQL
After storing the data in MongoDB, the project transfers the data to MySQL using a combination of insert queries and the pandas library.
MySQL is used for structured data storage and easy querying.

5. Query Execution with Streamlit
Streamlit is used to create an interactive web application where users can run predefined SQL queries on the MySQL database.
The user can select queries from a dropdown, and the results are displayed dynamically.

Tools Used
Python Libraries:

Pandas: Data manipulation and cleaning.
Json: Parsing configuration files (for column mappings and queries).
MySQL Connector: Connecting to MySQL and executing queries.
PyMongo: Interacting with MongoDB.
Streamlit: Building an interactive interface for running SQL queries.
Databases:

MongoDB: Used for storing raw and processed data.
MySQL: Used for structured querying and data analysis.
Files:

CSV: Raw data source.
JSON: Column mappings and SQL queries configuration.
Text: Files containing lists of specific districts for state renaming.

Execution Flow
1. Data Preparation
Step 1: Download the raw Census CSV file (census_2011_csv.csv) and place it in the project directory.
Step 2: Load column mapping file (column_mapping.json) to rename the columns according to MySQL table column names.
Step 3: Use the text files (telaganna_file.txt, Ladakh_file.txt) to update the state names for specific districts in Telangana and Ladakh.
2. MongoDB Setup
Step 1: Connect to MongoDB.
Step 2: Create a new MongoDB database (Census_db) and collection (census).
Step 3: Insert the cleaned data into the MongoDB collection.
3. MySQL Setup
Step 1: Connect to the MySQL database (Census_db).
Step 2: Use the DDL query (ddl_query.sql) to create a table in MySQL based on the column mapping.
Step 3: Fetch data from MongoDB and insert it into the MySQL table using the insert query (insert_query.sql).
4. Query Execution with Streamlit
Step 1: Use Streamlit to load and display a list of predefined SQL queries from a JSON file (queries.json).
Step 2: Users can select a query from the dropdown, execute it, and view the results.

How to Run the Project
1. Install Required Libraries
Ensure that the following libraries are installed:

 pandas
 pymongo 
 mysql-connector-python 
 streamlit
2. Set Up MongoDB and MySQL
MongoDB: Make sure MongoDB is running locally at localhost:27017 or update the connection string in the script if using a different setup.
MySQL: Set up MySQL with a database named Census_db or modify the connection details in the script if required.

3. Add Your Files
Add the following files to the project directory:
census_2011_csv.csv: The raw dataset.
column_mapping.json: A JSON file for column name mapping.
telaganna_file.txt, Ladakh_file.txt: Text files containing the districts for Telangana and Ladakh.
ddl_query.sql: SQL DDL query for creating the table in MySQL.
insert_query.sql: SQL insert query for transferring data to MySQL.
queries.json: JSON file containing the SQL queries to be run via Streamlit.

4. Run the Project
To execute the Streamlit web application:
bash
Copy code
streamlit cenusus_original.py
This will open the Streamlit app in your browser, where you can interact with the database and run queries.

---Folder Structure---

/project-directory
    /census_2011_csv.csv
    /column_mapping.json
    /telaganna_file.txt
    /Ladakh_file.txt
    /ddl_query.sql
    /insert_query.sql
    /queries.json
    /census_original.py
	
Contributing
Feel free to fork this project, contribute to improvements, and open issues for any bugs or feature requests.

This README file will provide a clear understanding of how to run the project and the workflow that connects MongoDB, MySQL, and Streamlit. It also serves as documentation for anyone wanting to set up and run the project locally or contribute to it.
