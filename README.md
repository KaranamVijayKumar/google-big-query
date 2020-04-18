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

## Agenda
1. Query a public dataset
2. Create a custom table
3. Load data into a table
4. Query a table

## Explore a BigQuery Public Dataset and Query it.

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

## Create a custom table

- Download the file [yob2014.txt](https://github.com/KaranamVijayKumar/google-big-query/blob/master/yob2014.txt).The file is a comma-separated value (CSV) file with the following three columns: name, sex (M or F), and number of children with that name.
- Create a dataset to hold your table, add data to your project.
- For Dataset ID, enter babynames, For Data location, choose United States (US)
- For Default table expiration, leave the default value and create dataset.

## Load the data into a new table










