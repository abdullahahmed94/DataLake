*Introduction

A music streaming startup, Sparkify, has grown their user base and song database even more and want to move their data warehouse to a data lake. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app In this project we will build an ETL pipeline that extracts their data from the data lake hosted on S3, processes them using Spark which will be deployed on an EMR cluster using AWS, and load the data back into S3 as a set of dimensional tables in parquet format From this tables we will be able to find insights in what songs their users are listening to.

*How to run

1-create a file dl.cfg in the root of this project with the following data:
    KEY=YOUR_AWS_ACCESS_KEY
    SECRET=YOUR_AWS_SECRET_KEY
    Create an S3 Bucket named sparkify-dend where output results will be stored.
2- run the following command:python etl.py

*Project structure

The files found at this project are the following:

dl.cfg: not uploaded to github - you need to create this file yourself File with AWS credentials.
etl.py: Program that extracts songs and log data from S3, transforms it using Spark, and loads the dimensional tables created in parquet format back to S3.
README.md: Current file, contains detailed information about the project.


Process data using spark
Transforms them to create five different tables listed under Dimension Tables and Fact Table. Each table includes the right columns and data types. Duplicates are addressed where appropriate.

Load it back to S3

Writes them to partitioned parquet files in table directories on S3.

Each of the five tables are written to parquet files in a separate analytics directory on S3. Each table has its own folder within the directory. Songs table files are partitioned by year and then artist. Time table files are partitioned by year and month. Songplays table files are partitioned by year and month.

