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

The data was filtered between participants that were paid reviewers in the vine program, denoted by "Y" in the "vine" column and reviewers who were not paid and not in the vine program, denoted by "N" in the "vine column.

A snippet of the breakdown of paid vs unpaid participants:

![vine breakdown](https://user-images.githubusercontent.com/110923091/208587384-ab62a850-b3be-4806-b4d2-6068caa960ac.PNG)

## Conclusion:

Based on the breakdown in the above snippet we can determine that, while paid reviews can introduce bias, there is not enough paid reviews to compete with the amount of unpaid reviews for Pet products. In total, there were 37,840 unpaid reviews and 170 paid reviews, with only 65 of those paid reviews being 5 star reviews. It's safe to assume that most reviewers are unbiased opinions. 


