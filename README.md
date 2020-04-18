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

# Demo Instructions

# Agenda
1. Query a public dataset
2. Create a custom table
3. Load data into a table
4. Query a table

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


