# Data Pipeline with Azure Data Factory

The goal of this project was to load a JSON file from S3, use the Function App to verify the data, and load verified file into Azure SQL Server.

Strategy Inspired by Udemy Course: 2 Real World Azure Data Engineer Project End to End

# Architecture Diagram
![Section 1_ Project 1_ Smart Vehicles](https://user-images.githubusercontent.com/121827505/216214568-7af3e6a8-ab59-4be0-bb92-3a9616724f8d.jpg)

# Project Setup

- JSON files are placed into the AWS S3 bucket which was then copied into a Landing folder in Azure DataLake Storage Account Container using Azure Data Factory Copy Pipeline
- The Function App stored a function used to validate the JSON within the files
    - Validation Requirements:
        - Writen in JSON format
        - No errors in JSON
        - Not incomplete
    - Validated JSON files are loaded into the staging folder
    - Unvalidated JSON files are loaded into the rejected folder
- Another Azure Data Factory Copy Pipeline was used to extract files from the staging folder and load the files into Azure SQL Server
- Azure Key Vault stored secrets, including access and secret acess keys used thoughout the project
- Project triggers when the first pipeline is manually triggered

# Data Analytics with PowerBI Desktop

The goal of this project was to load data to Power BI from different databases to create a Dashboard for data analysis. The dashboard represents the average speed of several vehicles and their location around the world

# Project Setup

- Data from different databases was uploaded into PowerBI Desktop
- Visualization tools including world map, gauge, and slicer were utilized for data analytics
  - World map displays the city location of each vehicle
  - Gauge displays the average speed of all the vehicles
    - When vehicle or country is selected the gauge shows the average vehicle of selected item
  - Vehicle ID slicer allows users to select a vehicle to analyze or displays vehicles located within the same country
  - Countries slicer allows users to select a country to analyze

![Screenshot 2023-02-05 101644](https://user-images.githubusercontent.com/121827505/216827911-68370d05-c55f-4dd8-b8dd-3155da65a74b.png)
