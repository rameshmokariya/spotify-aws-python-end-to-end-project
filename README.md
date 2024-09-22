# Spotify-AWS-Python-End-to-End-Data_Engineering-Project

### Introduction
In this Project, We Will Build an ETL (Extract,Transform,Load) Pipeline Using the Spotify API on AWS. The pipeline will retrieve data from 
the Spotify API, transform it to a desired format, and load it into an AWS Data Storage.

### Architecture
![Architecutre Diagram](https://github.com/rameshmokariya/spotify-aws-python-end-to-end-project/blob/main/Spotify-Python-AWS-Architecture.png)

### About API
This API Contains Information About Music Artists, Albums and Songs that Are trending in India. - [Spotify API](https://developer.spotify.com/documentation/web-api)

### Services Used
1. **S3 (Simple Storage Service):** Amazon S3 Service is a Highly Scalable Object Storage Service that can Store and Retrieve any Amount of of data from anywhere on the web. It is commonly used to store and Distribute Large Media Files, Data Backups, and Static Website Files.

2. **AWS Lambda:**  AWS Lambda is a Serverless Computing Service that lets you run your code without managing servers. You can Use Lambda to run code in response to events like changes in S3, DynamoDB, or other AWS Services.

3. **CloudWatch:** Amazon CLoundWatch is Monitoring Servie for AWS resources and the application you run on them. You can use Cloudwatch to collect and track mertics, collect adn montor log files, and set alarms.

4. **Glue Crawler:** AWS Glue Crawler is a fully managed service that automatically crawls your data sources, identifies data formats, and infer schemas to create and AWS Glue Data Catalog.

5. **Data Catalog:** AWS Glue Data Catalog is a fully managed metadata repository that makes it easy to discover and manage Data in AWS. You can use the Glue Data Catalog with other AWS Service, such as Athena.

6. **AWS Athena:** AWS Athena is an Interactive Query Service that makes it easy to analyze data in Amazon S3 using Standard SQL. You can use Athena to Analyze Data in Your Glue Data Catalog or in Other S3 Buckets.

### Install Packages
```
pip install pandas
pip install numpy
pip install spotipy
```

### Project  Excecution FLow 
A Lambda Function that Trigger every one Hour to Extract Data from API and Store RAW Data in S3 (to processed) 
-> as soon as Data Store in to-process Folder Cloudwatch Trigger Another Lambda Function that transform RAW Data into Desired Format and Store Data in transformed Folder and moves RAWS files from to-process to processed folder.
And We use Tranformed Folder to Data Catalog using Glue and Query Data using Athena for Analytics.


