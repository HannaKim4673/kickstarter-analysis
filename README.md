# Kickstarter Campaign Analysis

## Overview of Project

### Purpose
The purpose of this project was to help playwright Louise discover how well other kickstarter plays did, in terms of reaching their fundraising goals, in relation to the following two factors: the plays' launch dates and the plays' funding goals. In other words, this analysis was done to see if there is a visible relationship between a kickstarter play's launch date and success and a relationship between the funding goal for a kickstarter play and its success.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
To start, I created a column named "Years" in the "Kickstarter" worksheet, which is in the [Kickstarter_Challenge.xlsx](https://github.com/HannaKim4673/kickstarter-analysis/blob/main/Kickstarter_Challenge.xlsx.zip) Excel workbook, and used the YEAR() function to fill that column with the year values from the "Date Created Conversion" column. Next, the data in the "Kickstarter" worksheet was used to create a PivotTable in a new worksheet called "Theater Outcomes by LaunchDate." The PivotTable was set to be filtered by parent category and years and show the number of successful, failed, and canceled plays, which fall under the parent category of "theater," for each month of the year as seen here:   
![](https://github.com/HannaKim4673/kickstarter-analysis/blob/main/Theater%20Outcomes%20by%20Launch%20Date%20PivotTable.png)
Then, that PivotTable was used to create the following PivotChart:
![](https://github.com/HannaKim4673/kickstarter-analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
For this analysis, a new worksheet called "Outcomes Based on Goals" was created in [Kickstarter_Challenge.xlsx](https://github.com/HannaKim4673/kickstarter-analysis/blob/main/Kickstarter_Challenge.xlsx.zip). The following columns were created in that worksheet:
- "Goal"
- "Number Successful"
- "Number Failed"
- "Number Canceled"
- "Total Projects"
- "Percentage Successful"
- "Percentage Failed"
- "Percentage Canceled"

Next, the following ranges were created in the "Goal" column: less than 1000, 1000 to 4999, 5000 to 9999, 10000 to 14999, 15000 to 19999, 20000 to 24999, 25000 to 29999, 30000 to 34999, 35000 to 39999, 40000 to 44999, 45000 to 49999, and greater than 50000. After that, the COUNTIFS() function was used to find the number of successful, failed, and canceled plays in the "Kickstarter" worksheet that fall into the previously described goal ranges. For example, the find the number of successful plays that had a goal of less than $1,000, the following code was used: =COUNTIFS(Kickstarter!F:F, "successful", Kickstarter!D:D, "< 1,000", Kickstarter!R:R, "plays"). Then, the SUM() function was used to find the total number of plays that fall into each goal range, using the values in the "Number Successful", "Number Failed", and "Number Canceled" columns. Following that, the percentage of successful, failed, and canceled plays for each goal range were calculated using the values in the "Number Successful", "Number Failed", "Number Canceled", and "Total Projects" columns. Ultimately, the following table was created in the "Outcomes Based on Goals" worksheet:
![](https://github.com/HannaKim4673/kickstarter-analysis/blob/main/Outcomes%20Based%20on%20Goals%20Table.png)
Finally, that data in the "Goal", "Percentage Successful", "Percentage Failed", and "Percentage Canceled" columns were used to create the following line graph:
![](https://github.com/HannaKim4673/kickstarter-analysis/blob/main/resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered
