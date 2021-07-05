# kickstarter-analysis

# Kickstarting with Excel

## Overview of Project

Louise ran various campaign (total 4114) to raise funds concerning several patent categories such as film & video, theatre, music, photography, publishing, food, games, publishing, journalism and technology. The campaigns ran into various countries and gathered 463246 backers. Some campaigns ran successfully, reaching the campaign goal, some failed, some are still live and some eventually cancelled. 

With Kickstarter data, Louis wishes to know how different campaign fared to launch dates and their funding goals. With huge set of data items (4114 rows, and 14 columns), its easier for her to use excel features such as pivot, charts or countifs function to analyse the assorted dataset.

### Purpose

The purpose of this analysis is to identify following:
1.	In respective parent category for the respective year, how many (count) campaigns were successful, failed, canceled and live.  However, this module exercise aims to find out how the parent category “Theatre” has performed in each month in all campaign years concerning its outcome (except live). 
2.	Secondly, Louise wishes to understand, based on goal size and range, the percentages of each outcomes (except live)

## Analysis and Challenges

For Deliverable 1, Theater Outcomes by Launch Date – I used pivot table function (Selecting Kickstarter Dataset => Insert -=> Pivot Table and Pivot Chart) to assort the data based on "Parent Category" and "Years” and “Outcomes” as key parameters.  In pivot table fields, I assimilated the data in following way:  
•	Filters – Parent Category and Years – which I extracted out of date created conversion of launched_at UNIX Date dataset, 
•	Columns – outcomes to categorize the outcomes, 
•	rows – Date created conversion. 
•	Values – to show the count of campaigns based on each outcome that are extracted as columns.

Finally, I rechecked the overall data set number which should be 4064 (not including live projects) and theatre category must have 1369 data sets. This approves the validity of analysing all numbers in the data sets and no leftover data.

![image](https://user-images.githubusercontent.com/86085614/124415045-fb9d9580-dd21-11eb-8353-71d2ae876c8f.png)
![image](https://user-images.githubusercontent.com/86085614/124415053-048e6700-dd22-11eb-8f0f-281082fb7155.png)
![image](https://user-images.githubusercontent.com/86085614/124415068-0a844800-dd22-11eb-9ba8-e39bb958f925.png)
![image](https://user-images.githubusercontent.com/86085614/124415080-107a2900-dd22-11eb-87cb-d82f19801939.png)
![image](https://user-images.githubusercontent.com/86085614/124415093-15d77380-dd22-11eb-97ed-f79580ff5c99.png)

The challenges I encountered were understanding whether the Date created conversion will be used as rows or not. Initially, when I transported the date created conversion into rows section, it displayed the list of dates on which that campaign ran. But when I put years as the main filter – the data set arranged as per months as row variables.

The other challenge was sorting the campaign based on outcomes in descending order so "successful" is first. I was unable to find the sorting option, then I figured out that column labels can be sorted from Z to A as well. 

The possible challenge could be converting the “launched_at” into “Date Created Conversion” column with out studying the module beforehand. Converting that data would be difficult and would need the guidance of Instructor and TAs. 

For Deliverable 2, the Outcomes Based on Goals Chart has been prepared based on suing COUNTIFS function. As instructed, I created following columns:  Goal, Number Successful, Number Failed, Number Canceled, Total Projects, Percentage Successful, Percentage Failed, Percentage Canceled. I then assorted the goal column in 12 set of ranges as instructed in the module. For Number Successful column, I used following formulas to analyse the count of campaigns under the range and outcome category.

![image](https://user-images.githubusercontent.com/86085614/124415193-50411080-dd22-11eb-8d6b-cfae62c1ff25.png)
![image](https://user-images.githubusercontent.com/86085614/124415197-533c0100-dd22-11eb-9cff-f6d69377ff86.png)
![image](https://user-images.githubusercontent.com/86085614/124415204-5c2cd280-dd22-11eb-813e-6ad741ed1079.png)


For Goal, less than 1000, successful and plays as subcategory.
=COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"successful", Kickstarter!$R:$R, "plays") 

For Goal, more than equal to 1000, less tan equal to 4999, successful and plays as subcategory.
=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999",Kickstarter!$F:$F,"successful", Kickstarter!$R:$R, "plays")

Similarly, I extrapolated data for Number Failed and Number Canceled. 
Here the main challenge I faced was understanding the COUNTIFS function. It was overwhelming at first, as I sometimes dragged the formula from “less than 1000” to “greater than 50000” and result was absurd. Then I checked the $ sign I can put on selecting data criteria for COUNTIFS function. This process made my analysis easier for Number Successful column. However, for repeating the same formula for Number Failed and Number Canceled, I used Ctrl + f command to replace “Successful” to “failed” or “Canceled” in formula text. 

This way I did the entire analysis in 3 minutes. Rest Adding up the data in Total Projects and obtaining Percentage Successful, Percentage Failed and Percentage Canceled was easy process.

The other issue I felt was typing tharange criteria in the COUNTIFS formula. For example, =COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999",Kickstarter!$F:$F,"successful", Kickstarter!$R:$R, "plays")

Here in each 12 range, I typed the >=1000 or <=49999 manually. This could be easier and non time consuming if I knew the better linking option. So that no matter what my range is I can conclude any amount of data. 


### Analysis of Outcomes Based on Launch Date

The overview of the Deliverable 1 is based on extracting data for Parent category theatre and understanding the outcomes based on the campaign’s launch Date (month wise). Overall, the month of May there has been the greatest rise in successful campaigns. In October month, no campaign has been cancelled.
![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/86085614/124415364-b0d04d80-dd22-11eb-8ea3-965b6c95e34e.png)

### Analysis of Outcomes Based on Goals

For Deliverable 2, Louise wishes to understand the percentage breakup of outcomes (successful, canceled and failed) with a set range of goals. The analysis has shed the light on following information: 
•	The maximum successful campaign in comparison to failed campaign were within the less than 1000 and 1000 to 4999 goal ranges. (76% and 73% respectively)
•	 As the goal range went beyond greater than 45000, the deals were failed on higher percentages (>88%).
•	At 15000 to 19999 range, there were equal distribution between failed and successful campaigns.
•	There are no cancelled campaigns under plays subcategory.
![Outcomes_vs_Goals](https://user-images.githubusercontent.com/86085614/124415335-a57d2200-dd22-11eb-8739-603c040975bc.png)


### Challenges and Difficulties Encountered

•	In Deliverable 1, The challenges I encountered were understanding whether the Date created conversion will be used as rows or not. Initially, when I transported the date created conversion into rows section, it displayed the list of dates on which that campaign ran. But when I put years as the main filter – the data set arranged as per months as row variables. The other challenge was sorting the campaign based on outcomes in descending order so "successful" is first. I was unable to find the sorting option, then I figured out that column labels can be sorted from Z to A as well. 

•	In Deliverable 2, the main challenge I faced was understanding the COUNTIFS function. It was overwhelming at first, as I sometimes dragged the formula from “less than 1000” to “greater than 50000” and result was absurd. Then I checked the $ sign I can put on selecting data criteria for COUNTIFS function. This process made my analysis easier for Number Successful column. The other issue I felt was typing the range criteria in the COUNTIFS formula. For example, =COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999",Kickstarter!$F:$F,"successful", Kickstarter!$R:$R, "plays"). Here in each 12 range, I typed the >=1000 or <=49999 manually. This could be easier and non time consuming if I knew the better linking option. So that no matter what my range is I can conclude any amount of data. 


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

•	Compared to other months, May and June had the most successful campaigns (111 and 100). 
•	There were no deals that are canceled in October month for theatre parent category.


- What can you conclude about the Outcomes based on Goals?

•	Out of 12 ranges, in 5 ranges there were more failed campaigns % than successful.
•	 Less than 1000 range has the most succeful % of campaigns than failed.


- What are some limitations of this dataset?

•	The launched date was in UNIX method, and it needs to be converted through formula or UNIX convert into readable date format.
•	The goal $ data is spread between $1 to $100,000,000 which extremely skewed and unsymmetric and both extremes are proving to be as outliers. Same is the case with pledged data.
•	The parent category and subcategory were initially merged. Without the understanding of module 1 exercises, it would be difficult to separate the parent and subcategory data set.
•	The following data points are unused and in excess, currency, deadline and staff_pick


- What are some other possible tables and/or graphs that we could create?
We could create Category Statistics, Subcategory Statistics, Outcomes Based on Launch Date – Parent and subcategory wise, Kickstarters – country wise, Kickstarters – outcome wise, Kickstarters – goals outcomes – currency wise.
