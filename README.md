# Kickstarting with Excel

## Overview of Project 

Louise is a budding playwright who wants to crowdfund her play "Fever". She is estimating upwards of $10,000 to get the play into production and live. Her play came close to its fundraising goal in a short amount of time. 
Louise now wants to find out how different campaigns have fared 
1. In relation to to their launch dates
2. In relation to their funding goals

There is a kickstarter excel sheet available which has campaign data spanning across genres, date launched, countries, pledged and goal amounts, outcomes and backers. This sheet would be used to provide the required details to Louise.

### Purpose

The purpose of the project is to provide Louise with the information of how different campaigns have fared with respect to their launch dates and funding goals, so that she is able to take a decision which is best for her crowdfunding campaign to be successful

## Analysis and Challenges

The analysis has been done on the Kickstarter sheet.
The Kickstarter sheet has campaign data spanning across genres, date launched, countries, pledged and goal amounts, outcomes and backers.

The below screen shots show the data in the sheet

The data in the sheet is across campaigns and years

![image](https://i.imgur.com/wTg1RIn.png)

The data in the sheet is across outcomes, countries,currencies and unix date timestamps

![Screen Shot 2021-05-07 at 6.45.14 PM](https://i.imgur.com/EYAu5EF.png)

First, unix time stamp dates have been converted to readable date by using the below code:
=(((I2/60)/60)/24)+DATE(1970,1,1)

Using this formula, the "deadline" and "launched at" field data have been converted to readable dates "Date Created Conversion" and "Date Ended Conversion"

The below screen shot shows these fields:
![Screen Shot 2021-05-07 at 6.51.55 PM](https://i.imgur.com/uIBA7XM.png)

After this conversion the column "Years" is derived from the "Date Created Conversion"  column, using YEARS() function. This "Years" field is used in the generation of the "Outcomes Based on Launch date Report"
![Screen Shot 2021-05-07 at 7.03.11 PM](https://i.imgur.com/tgXVcPi.png)

In order to create the data required for "Outcomes Based on Launch Date", the pivot table has to be created with the "Date Created Conversion" field as the row, and the "Outcomes" as the column. The table has to be filtered on "Parent Category" and "Years". This ensures, that we have the outcomes available per month, and helps us to analyze the outcome as per the launch dates of the campaign.

The below screen shot shows the attributes used in the creation of the required data/chart:
![Screen Shot 2021-05-07 at 7.15.36 PM](https://i.imgur.com/8ZLcN3Q.png)

In order to create the "Outcomes Based on Goals" data, the counts of the campaigns which are "plays", as per the range of the goal amount and outcomes has been calculated.
In order to do so, we have used the COUNTIFS() function. Also, the percentage successful and percentage failed for each range has been calculated. This is to ensure that there is relevant data to indicate the number and percentage of successful and failed campaigns which are "plays".

The code to find out the counts as per outcomes and goal amount range for the "plays" is shown in the below screen shot:
![Screen Shot 2021-05-07 at 7.21.47 PM](https://i.imgur.com/s3b51zZ.png)


The challenges in analysis and creating the outcome data are as follows:
1. Converting the Unix Time Stamp to Readable Dates.
2. Using the COUNTIFS() function


### Analysis of Outcomes Based on Launch Date

The analysis show that the successful campaigns for "Theater" are at the peak of success in the months of May and June. From July onwards, the number of successful campaigns begin to decline, except in October. The least number of successful campaigns happen in the month of December. The number of successful campaigns is almost steady in the months of January till April.
The failed campaigns are also at their highest numbers during the month on May and June.
This shows that the maximum number of campaigns for "Theater" are launched during the month on May and June.
The failed campaigns also begin to decline from August till December barring October. The failed campaigns are almost steady from January till April.
The maximum number canceled campaigns for "Theater" occur in the month of January.
There are no canceled campaigns in the month of October.

![Screen Shot 2021-05-07 at 7.47.23 PM](https://i.imgur.com/357Ijco.png)


### Analysis of Outcomes Based on Goals

This analysis is for the subcategory "plays".
The analysis of this data shows that the maximum number of successful campaigns occur when the campaign goal range is between 1000 to 4999 dollars. Also the maximum number of campaigns is launched in this range.This range however also has the maximum number of failed campaigns. With a success percentage of 72.66, this range is a feasible range to launch a successful campaign.
The second most number of successful campaigns is in the range less than 1000 dollars. It also has the second most number of campaigns launched. With a success percentage of 75.81%, it is also a feasible goal range to launch a successful campaign.
The third most number of successful campaigns,93, is in the range between 5000 and 9999. However it also has a large number of failures, 76, when compared to success. This might be a feasible range to launch campaigns which have a goal greater than 5000 dollars. The success percentage is 55.03.
In the range from 10000 to 14999 dollars, the success percentage is 54.17 which seems to be decent number based on the donation goal.
The number of campaigns greater than 15000 are less in number. However the campaigns from 35000 to 39999 dollars have a higher success percentage of 66.67. 
The highest percentage of failures is in the range greater than 50000 dollars.

There are no campaigns which have been canceled.
![Screen Shot 2021-05-07 at 8.12.38 PM](https://i.imgur.com/fM4G9ab.png)

### Challenges and Difficulties Encountered

The challenges are as follows:
1. Sorting out the campaigns on the basis of their outcomes in the "Theater Outcomes By Launch Date" sheet. 
2. In the "Outcomes Based on Goal" data calculating the counts of the campaigns based on the goal range, outcome and sub-category. Also analyzing the data on the combination of number of ranges and outcomes.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

1. For the parent category "Theater", the months of May and June are the most feasible months to launch a campaign. Louise can try to launch her campaign in these two months.
2. For the parent category "Theater", it can be recommended that the campaign be launched in between the months of April and October. Louise also has this month range where she can launch her campaign.

- What can you conclude about the Outcomes based on Goals?
For the subcategory "Plays" (of the category "Theater"), the most successful campaigns have goal ranges from less than 1000 dollars to 10000 dollars. Louise has more than 54 percentage chance of a successful campaign as her dollar amount is upwards of $10000


- What are some limitations of this dataset?
The quantity of the data is a limitation. Also, there is not enough data for campaigns above $10000. 

- What are some other possible tables and/or graphs that we could create?
Box and Whiskers graph can be created to determine the outliers. We can also create a pivot graph only on "Theater"  and outcomes to determine the successful campaigns
