# pandas-challenge

# PyCitySchools

## Task

Analyze the district-wide standardized test results. You'll be given access to every student's math and reading scores, as well as various information on the schools they attend. Your task is to aggregate the data to showcase obvious trends in school performance.

Using Pandas and Jupyter Notebook, create a report that includes the following data. Your report must include a written description of at least two observable trends based on the data.

## District Summary

Perform the necessary calculations and then create a high-level snapshot of the district's key metrics in a DataFrame.

Include the following:

Total number of unique schools

Total students

Total budget

Average math score

Average reading score

% passing math (the percentage of students who passed math)

% passing reading (the percentage of students who passed reading)

% overall passing (the percentage of students who passed math AND reading)

## School Summary

Perform the necessary calculations and then create a DataFrame that summarizes key metrics about each school.

Include the following:

School name

School type

Total students

Total school budget

Per student budget

Average math score

Average reading score

% passing math (the percentage of students who passed math)

% passing reading (the percentage of students who passed reading)

% overall passing (the percentage of students who passed math AND reading)

## Highest/Lowest-Performing Schools (by % Overall Passing)

Sort the schools by % Overall Passing in descending/ascending order and display the top 5 rows respectively.

Save the results in two seperate DataFrames called "top_schools" and "bottom_schools" respectively.

## Math and Reading Scores by Grade

Perform the necessary calculations to create two seperate DataFrame that lists the average math and reading scores for students of each grade level respectively.

## Scores by School's Spending, Size, and Type

Using bins, categorize each of the school's spending, size, and type by each school's average scores. Create a dataframe for each to display each for analysis.

## Written Report

Summarize the analysis and draw on two correct trends, conclusions, or comparisons from the calculations.

## Description

I started by importing the dependencies, set up the files, merged the files into an initial dataframe and displayed the first five results with the code provided. I returned the total number of schools and students by using the .count() function over the school name and student name columns respectively. Using the .sum() function over the budget column it returned the total budget for the school district. To calculate the average reading and math scores for each student I used the .mean() function over each score repsectively. Using the code provided, I calculated the percentage of students that passed math which had a condition of having a math score greater than or equal to 70. Counting those scores based on student name and then dividing by the total number of students to determine the percentage that passed math. I used the same code to determine the percentage of students that passed reading under the same condition. I then created a dataframe that displayed the calculations above with the formatting provided. I started the school summary by grouping the initial dataframe by school name. To determine the school type for each school, I used the .first() function to return the first value that meets the criteria. To calculate the total student count per school I used the .couunt() again using the student name column. To calculate the the budget per student, I first determined the budget for each school and then divided that by the total number of students per school. I then calculated the average reading and math scores per school. Then using the code used previously to return the passing percentage in the district summary, this time I grouped by the school name, counting the math score of each student, taking that result and dividing by the total number of students per school to return the number of students per school passing math as a percentage. I did the same to return the number of students per school passing reading as a percentage. I used the code provided to calculate the number of students per school that passed both math and reading as the overall passing rate. I used the code provided for the passing rates per school as a percentage. I then created a dataframe to display the calculations with the formatting provided. I specifically used the school students passing math and reading respectively as the % Passing Math and Reading as this was the accurate calculation per school. I sorted the per school summary using the .sort_values() based on the overall passing percentage to determine the top 5 and bottom 5 performing schools. I used the code provided to sperate the data by grade. Then grouping by the school name for each grade, I calculated the average math score of each student. I then created a dataframe and displayed the results. I did the same to create and display the reading results based on each grade per school. Using the bins provided, I started categorzing the data based on spending. I created a copy of the per school summary with the code provided. I noticed using the pd.cut() function to sort spending per student budget into their repsective range was returning an error. This was due to the value in the column being a string. To sort into a bin I first needed to convert the data type into a float. Before doing this I had to remove the $ from the per student budget column in order to assign the data type to the values in the column. Once complete I displayed the results in a dataframe returning the spending ranges per student based on school. I then grouped by these ranges and the average score results, assembled these results into a dataframe and displayed the average scores based on spending ranges. I used similar coding to return the average scores based on both school size and school type. Although this time the values for those respective columns did not need their data type changed. I then wrote a written analysis drawing two conclusions based on trends and comparisons I noticed from the data summaries compiled.

## References

Reference for .first() function

https://www.w3schools.com/python/pandas/ref_df_first.asp#:~:text=The%20first()%20method%20returns,based%20on%20the%20specified%20value.

Reference for .sort_values() function

https://www.w3schools.com/python/pandas/ref_df_sort_values.asp - Lines 21 and 22 of PyCitySchools_starter.iypnb code

Reference for removing dollar sign with Pandas in python

https://stackoverflow.com/questions/38516481/trying-to-remove-commas-and-dollars-signs-with-pandas-in-python - Line 27 of PyCitySchools_starter.iypnb code

