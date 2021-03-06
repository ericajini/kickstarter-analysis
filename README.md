# Kickstarting with Excel

## Overview of Project

  Louise wants to compare different Kickstarter campaigns to have a better understanding of how to approach a campaign for her play fever. I completed an analysis on different Kickstarter campaigns related to theater to explain the different outcomes based on Launch Date and the Goal. This analyis includes a combination of formulas, pivot tables, and pivot charts to represent the data for the outcomes mentioned above. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

  To complete this part of the analysis I created a pivot table from the Kickstarter data sheet using Successful, Failed and Canceled columns and the months of the year as the rows. The table shows how many Kickstarters fall in each category month over month. There is also a filter set for the Parent Category to be theater so we are only showing the data that is related to the play Louise is working on, and a filter for Years if the data needs to be broken down further. This pivot table was used to create a line pivot chart to help visualize what the data is telling. In the pivot chart the x-axis represents the months, the y-axis represents the number of outcomes and the lines are a different color for successful, failed and canceled. This makes it easier to see how the kickstarters are trending over time. 
  
  ![Outcomes Based on Launch Date](https://github.com/ericajini/kickstarter-analysis/blob/main/reference1.1.png)
  
### Analysis of Outcomes Based on Goals

  To complete this part of the analysis I created a table with the columns displaying the number of successful, failed, and canceled Kickstarters campaigns as a number and as a percentage. The rows in the table represent ranges of goals for the campaigns. To get the correct data I used COUNTIFS formulas to pull the total numbers from the Kickstarter data sheet flitering based on the goal range outlined in the rows, the outcome of the campaign and the Subcategory, plays. An example of the formulas used are below.. 
  
    Number Successful`=COUNTIFS(KickStarter!D:D,"<1000", KickStarter!F:F, "Successful", KickStarter!O:O, "plays")`
    Number Failed: `=COUNTIFS(KickStarter!$D:$D,">=10000", KickStarter!$D:$D,"<=14999", KickStarter!$F:$F, "failed",         KickStarter!$O:$O, "plays")`
    Number Canceled: `=COUNTIFS(KickStarter!$D:$D,">=1000",KickStarter!$D:$D,"<=4999",KickStarter!$F:$F,"canceled,           KickStarter!$O:$O, ""plays")`


  I used the data from those formulas to calculate the total campaigns and the percentages for the successful, failed and canceled kickstarters. The totals of those 3 categories are each divided by the total number of projects based on the goal range. An example of the formulas used are below: 
  
    Percent Successful:`=IFERROR((B2/E2),0)` 
    Percent Failed: `=IFERROR((C2/$E$2),0)`
    Percent Canceled: `=IFERROR((D2/$E$2),0)`

  This table was also used to create a pivot chart to help visualize what the data is telling. The x-axis represents the ranges of goals while the y-axis represents the percentage, and the lines are different colors to represent the successful, failed and canceled kickstarter campaigns. This makes it easier to see the goal range where kickstarters are more successful.  
  
  ![Outcomes Based on Goal](https://github.com/ericajini/kickstarter-analysis/blob/main/reference2.png)

### Challenges and Difficulties Encountered
  
  During this analysis I had the most difficulty creating the formulas, specifically the COUNTIFS formulas. There was a lot involved with creating the initial formula to use and I ended up using the range of rows for pledged amount instead of using the range of rows for goal, which led to some confusion when it came to the chart because it was not matching the module. I think it was also a little difficult to get only the months of the year to show up in the Theater Outcomes by Launch Date sheet pivot. 

## Results

### What are two conclusions you can draw about the Outcomes based on Launch Date?

1. The most successful Theater Campaigns happen in May and trend downward for the rest of year, outside of a minor increase in October.

2. The least successful Theater Campaigns happen in November, but there are consistently more successful Theater Campaigns than failed Theater Campaigns month over month. 

### What can you conclude about the Outcomes based on Goals?

  I think the most important point to make is that Theater Campaigns for plays are most successful when the goal is less than $1000.00 at close to 76 %. There is a downward trend from there for the most part outside of a spike above 60% between $35,000.00 and $44,999.00. Beyond that the success rate drops very quickly and the failure rate shoots up, even to 100% at one point. Also for the plays Sub-category, there were no canceled Kickstarters. 

### What are some limitations of this dataset?

  In the Outcomes Based on Goals sheet we are filtering by the Sub-Category, plays, but in the Theater Outcomes by Launch Date sheet we are only filtering by the Parent Category, theater. I think this could slightly change the results for the Theater Outcomes by Launch Date if we updated it to plays, but still think the outcome would remain generally the same since the plays Sub-Category is factored into the Parent Category, theater.
  
   Another limitation of this data set is that some of the data being used to come to these conclusions are from 2009, so 13 years ago. If this is a play Lousie is looking to do in 2022, we may consider only the last 2-3 years of data to be revelant so that we are able to focus on more recent trends and things revelant to pop culture that could have a better chance of succeeding since it's what people are looking for at that time.   
  
  Also, In the Outcomes Based on Goals sheet, the data tends to be showing that as the goal goes up, the failure rate goes up, that is until around $35,000.00 to $44,999.00. There is not enough info based on that table/ chart to determine what other factors are impacting that change like if those campaigns happened to launch in May, where we seen that the success rates are higher, or if the play is a specific genre causing it to gain traction. 

### What are some other possible tables and/or graphs that we could create?

  Related to what I mentioned above, I think we could also use a stacked bar graph with percent on the y-axis (to represent percentage of success), the months of the year on the x-axis and different colors for each goal range. I think this could be used to see if the launch date may have a difference on the goals at the higher amounts and if you could maybe be more successful if you launched a campaign with a goal between $35,000.00 to $44,999.00 in like May. I think we could also do another stacked bar graph but replace the x-axis with Country so we can see if depending on the Country the campagin is launched in, does that have an impact on the goals at higher amounts. I also think it would be interesting to define the genres more and use this info to see if plays are more successful when taking into account seasonal changes (for example, does a kickstarter campaign for a play about "love" have better success if it was launched in Feburary around Valentines day?). 
