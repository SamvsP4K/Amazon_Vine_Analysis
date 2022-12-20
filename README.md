# Amazon Pet Products Vine Program Bias Analysis

## Purpose:

The purpose of this analysis was to take a dataset from an S3 bucket, clean the data, and store it in a Postgres SQL database that is hosted in an AWS instance.

[Link to the S3 bucket used](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Pet_Products_v1_00.tsv.gz)

## Cleaning and Storing Process:

A schema for required tables was imported into Postgres. There was a total of 4 tables created. One for customers, poducts, review IDs, and a vine  program table.
Using Pyspark in a Google Colab environment the tables with the appropriate data were extracted from the S3 bucket, duplicate data was dropped, and columns that were not needed for this analysis were left out.

Once the necessary data was extracted it was imported to Postgres from the Colab notebook.

## Vine Bias Analysis 

For the Vine Bias analysis we observed only the table that was created for the Vine program.

Preview of Vine Program table:

![vineprogramtable](https://user-images.githubusercontent.com/110923091/208584554-d5939f5c-46d3-4f93-af4e-20a4fccd7bef.PNG)





