# School District Analysis

## Description
Thisd project conducts an analysis on school and student performance within a school district. It combines datasets of school and student information to provide key metrics, such as overall passing rates, average scores, and performance based on school spending, size, and type.

## Dependencies
* pandas

## Usage
1. Ensure you have the pandas library installed.
2. Clone this repository.
3. Place the schools_complete.csv and students_complete.csv files in a folder named Resources in the project directory.
4. Run the script to perform the analysis.

## Loading Data
The code begins by loading the school and student data from CSV files into pandas DataFrames:

```python```
import pandas as pd 
from pathlib import Path

## Define the paths to the CSV files
school_data_to_load = Path("../Resources/schools_complete.csv")
student_data_to_load = Path("../Resources/students_complete.csv")

## Read the CSV files into pandas DataFrames
school_df = pd.read_csv(school_data_to_load)
student_df = pd.read_csv(student_data_to_load)

## Data Merging
The student and school DataFrames are merged using a left join on the school name to create a complete dataset:

```python```
school_data_complete = pd.merge(student_df, school_df, how="left", on=["school_name", "school_name"])

## District Summary Metrics

The code calculates various metrics for the entire district:
*Total number of unique schools
*Total number of students
*Total budget
*Average math score
*Average reading score
*Percentage of students passing math
*Percentage of students passing reading
*Overall passing rate

## School Summary
The code groups the data by school name to calculate:
*School types
*Total students per school
*Total school budget and per capita spending
*Average math and reading scores
*Percentage passing math, reading, and overall

## Top and Bottom Performing Schools
The code identifies the top 5 and bottom 5 performing schools based on overall passing rate.

## Scores by Grade
The code separates and calculates average math and reading scores for each grade level (9th, 10th, 11th, 12th).

## Scores by School Spending
The code categorizes schools into spending ranges per student and calculates average scores and passing rates for each range.

## Scores by School Size
The code categorizes schools into size categories (small, medium, large) and calculates average scores and passing rates for each category.

## Scores by School Type
The code groups schools by type (Charter, District) and calculates average scores and passing rates for each type.

## Output
The analysis results are displayed as DataFrames and can be further analyzed or exported as needed.

## PyCitySchools Folder: 
1. main.py --> Contains python pandas script for the school data anaylsis for this assignment 
2. Written Analysis --> Contains the summary anaylsis and key conclusions of the data analysis 
3. Resources folder --> Contains the csv file from which the data was acquired

## Credits: 
GeeksforGeeks: Provided insights into the first() method and its usage for selecting the first element of each element set.
Stack Overflow: Assisted in devising a method to remove the dollar sign from a DataFrame column, facilitating the conversion of the column from an object to a float data type.

