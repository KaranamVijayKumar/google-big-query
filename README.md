# google-big-query
This repo is created to demonstrate Google Big Query as part of our workshop presentation in Big Data course.

# Google BigQuery Workshop

- Course & Section: 44517-01
- Group 5 

# Team Members

- [Vijay Kumar Karanam](https://github.com/KaranamVijayKumar/)
- [Prajakt Uttamrao Khawase](https://github.com/Prajakt-Khawase)
- [Harsha Vardhan Reddy Nallavolu](https://github.com/harsha4824)
- [Lavanya Reddy Uppula](https://github.com/reddylavanya)

# Links

- [Source](https://github.com/KaranamVijayKumar/google-big-query)
- [Demo](https://karanamvijaykumar.github.io/google-big-query/)
- [PowerPointPresenatation](https://github.com/KaranamVijayKumar/google-big-query/blob/master/Google%20BigQuery.pptx)
- [A Deep Dive Into Google BigQuery Architecture](https://cloud.google.com/files/BigQueryTechnicalWP.pdf)
- [Columnar database](https://www.stitchdata.com/columnardatabase/)

# Columnar format and Advantages
- A columnar database is a database management system (DBMS) that stores data in columns instead of rows. 

- The goal of a columnar database is to efficiently write and read data to and from hard disk storage in order to speed up the time it     takes to return a query.  

- In a columnar database, all the column 1 values are physically together, followed by all the column 2 values, etc. The data is stored   in record order, so the 100th entry for column 1 and the 100th entry for column 2 belong to the same input record. This allows           individual data elements, such as customer name for instance, to be accessed in columns as a group, rather than individually row-by-     row. 

- One of the main benefits of a columnar database is that data can be highly compressed. The compression permits columnar operations —     like MIN, MAX, SUM, COUNT and AVG— to be performed very rapidly.  Another benefit is that because a column-based DBMSs is self-         indexing, it uses less disk space than a relational database management system (RDBMS) containing the same data. 

# Demo Instructions
# Agenda
1. Query a public dataset.
2. Create a custom table.
3. Load data into that custom table.
4. Query the custom table you created.

# Explore a BigQuery Public Dataset and Query it.

- In the Google Cloud Console, select Navigation menu > BigQuery:
- In the left pane, click ADD DATA > Explore public datasets.
- In the searchbox, type USA Names then Enter. 
- Click on the USA Names tile you see in the search results and view Dataset.
- Copy and paste below query into Query Editor and run it.

SELECT
  name, gender,
  SUM(number) AS total
FROM
  `bigquery-public-data.usa_names.usa_1910_2013`
GROUP BY
  name, gender
ORDER BY
  total DESC
LIMIT
  10

# Create a custom table.

- Download the file [yob2014.txt](https://github.com/KaranamVijayKumar/google-big-query/blob/master/yob2014.txt).The file is a comma-separated value (CSV) file with the following three columns: name, sex (M or F), and number of children with that name.
- Create a dataset to hold your table, add data to your project.
- For Dataset ID, enter babynames, For Data location, choose United States (US)
- For Default table expiration, leave the default value and create dataset.

# Load the data into a new table.

- Click babynames found in the left pane in the Resources section, and then click Create table.
- For Source, choose Upload from the Create table from: dropdown menu.
- For Select file, click Browse, navigate to the yob2014.txt downloaded file and click Open.
- For File format, choose CSV from the dropdown menu.
- For Table name, enter names_2014.
- In the Schema section, click the Edit as text toggle and paste the following schema definition in the text box and click create table.

- name:string,gender:string,count:integer

# Query the custom table.

- In the Query editor, click Compose new query.
- Copy and paste the following query into the Query editor. This query retrieves the top 5 baby names for US males in 2014 and click run.

SELECT
 name, count
FROM
 `babynames.names_2014`
WHERE
 gender = 'M'
ORDER BY count DESC LIMIT 5

#### Congratulations! You queried a public dataset, then created a custom table, loaded data into it, and then ran a query against that table.


