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
While analyzing the relationship between play outcomes and launch dates, I encountered a few minor challenges. One of those challenges was that I forgot exactly how to access the PivotTable feature in Excel without referencing the module. Eventually, I did find it after searching in the Excel tabs I thought were likely to house the feature. Also, since I am rather new to using PivotTables, I had some trouble figuring out exactly which fields from the "Kickstarter" worksheet data should go in which area of the PivotTable without referencing the module. Thankfully, after a little trial and error and digging through my memories, I was able to figure out that outcomes were supposed to be in the columns and values areas while "Date Created Conversion" was supposed to be in the rows area. Likewise, I also had a little trouble remembering how to create a PivotChart **after** creating a PivotTable, but I was able to recall the method after a couple seconds. On the other hand, I only expereinced one challenge while analyzing the relationship between play outcomes and play goals. Essentially, when I copied and pasted the COUNTIFS() function I used to calculate the values for one of the columns in the "Outcomes Based on Goals" worksheet into the next column - e.g., copying the code used in the "Number Successful" column in to the "Number Failed" column - for some reason, the cell ranges increased by one. For example, when =COUNTIFS(Kickstarter!F:F, "successful", Kickstarter!D:D, "< 1,000", Kickstarter!R:R, "plays") was copied from one column to the adjacent one, the cell ranges increased by one and the code became =COUNTIFS(Kickstarter!**G:G**, "successful", Kickstarter!**E:E**, "< 1,000", Kickstarter!**S:S**, "plays"). Thankfully, this challenge was easily overcome by manually adjusting the ranges each time the code was copied, but this process was cumbersome and always produced the fear that the rest of the code may be accidentally altered in the process of editing the ranges.

## Results

### 2 Theater Outcome by Launch Date Conclusions
Looking at the "Theater Outcomes Based on Launch Date" line graph below, it can be conluded that there is a greater chance of a play succeeding if it is launched in either May or June, since those are the months with the greatest difference between the number of plays that were successful and the ones that failed. Another conclusion that can be drawn is that December is the worst time of the year for launching plays, since the number of plays that were successful and the number of plays that failed are almost equal as seen in the below graph.
![](https://github.com/HannaKim4673/kickstarter-analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png)

### Outcomes Based on Goals Conclusion
Meanwhile, the "Outcomes Based on Goal" line graph below shows that in general, the lower the funding goal is for play, the more likely it is that the play will succeed. However, it also appears that plays with funding goals between $35,000 and $49,999 are also quite successful, but even then, they are not as likely to succeed as plays that have funding goals less than $1,000, as seen in the below graph.
![](https://github.com/HannaKim4673/kickstarter-analysis/blob/main/resources/Outcomes_vs_Goals.png)

### Limitations of Dataset
The dataset used in these analyses does have 2 main limitations. One is that the plays included in this dataset were all launched between the years of 2009 and 2017. While this dataset is able to show trends for plays in that time period, it is not necessarily reflective of future trends, since relationships and effects can change over time. The other limitation is that the plays, and other campaigns in general, included in this dataset are mostly from countries where English is a primary language, such as the United States and Great Britain. While there are some campaigns that are from countries where English is not a primary language, there do not appear to be too many of them. As a result, any conclusions drawn from this dataset cannot easily be generalized to outcomes of campaigns all over the world.

### Other Possible Tables and Graphs
It may actually be beneficial to create a stacked bar graph for the theater outcome by launch date analysis, since that would make it easier to compare the number of successful, failed, and cancelled plays in a given month. Furthermore, if the analysis does not have to be limited to launch dates and funding goals, I think it would be beneficial to also analyze the relationship between a play's success, the number of backers it had, and what its funding goal was. After all, the number if backers a play had could very well have impacted whether or not a play was able to meet its goal and be successful. To that end, it would be beneficial to create a PivotTable and a stacked bar graph for those 3 variables.
