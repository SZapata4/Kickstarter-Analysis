# An Analysis of Kickstarter Campaigns

## Overview of Project 
  Performing Analysis on Kickstarter Data to uncover trends based on their goal amounts, launched dates, and countries they are in.

### Purpose
  The purpose of this traing was to analysis the data so that louise can have a guide on how to plan a successful Kickstarter. 

## Analysis and Challenges
  We analyzed the data in a few different ways. One was by looking at outcomes based on their goals. The other was lookoing at their outcomes based on the launch date for louise specific subcategory.
### Analysis of Outcomes Based on Goals
  We started this analysis by setting ranges of goals for the Kickstarters. Starting with less than a thousand then grouping them in $5,000 incremnts until we end with $50,000 or more for goals. From there we used the following COUNTIFS function to pull the number of succeful, failed, and cancelled kickstarters for each range. 
  =COUNTIFS(kickstarter!$F:$F,"=successful",kickstarter!$D:$D,"<1000",kickstarter!$R:$R,"=plays")
By subbing out the "=successful" with cancelled and failed we could pull the count for those columns as well. Once that was complete looked at the total number of projects for each range of goals using the Sum() function. With that we are able to find the percentage Successful, failed, and canceled for each range of goals by dividing succeful, failed, and canceled by the total. We then used that to create the below chart to give louise a visual look at what we found using Pivot Charts.

### Analysis of Outcomes Based on Goals
  We started this analysis by converting the starting date and end date data from Unix timestamps to day-month-year format that we can interpret. We accomplished that by using the below formula.
  =(((J2/60)/60)/24)+DATE(1970,1,1)
From that point we created a pivot table as well as a chart by Filtering by parent category and years, making the Columns value to be "outcome," Rows value to be "Date Created Conversion," and Values to be "outcome.". That gave us the below chart that is able to be filtered by parent category as well as years to see how certain kickstarters did while starting at different months of the year.

### Challenges and Difficulties Encountered
  The biggest problem we ecnountered during this analysis was errors in the initial COUNTIFS functions. We could not get a number to populate at first due to using multiple <>= signs. Once i simplified the code to using one of each we were able to get the correct totals to populate.
  
## Results
  From all of the data we've gatherd and analyzed here we can come away with a few conclusions. Firs looking at Outcomes based goal chart we cam concluded that from the less than $1,000 to $19,999 you have a higehr chance of your kickstarter succeeding than it failing. However the gap does close the closer you get to that $15,000-$19,999 goal point. From there to just before the $35,000 to $39,999 goal point your kickstarter has a better chance at failing than succeeding. Then from that point to a little bit past the $40,000 to $44,999 Goal point it flips and your kickstarter has a better chance at suceeding than failing. From that point on if your goal is $50,000 or more your kickstarter has a slim chance of succeeding.
When it comes to the outcomes based on launch date data there are also a few can conclusions we can make. First it is clear that if you start your project in February or May your hava a very high chance of your your kickstarter succeed. The opposite is true for the months of December and September those the months with the lowest number of success projects. Those months are also the two months where the number failed projects is either more or closeer than any other month. 
With that being said our data doe shave some holes. With the outcomes based on launch date we do not factor in the closing date which I believe would tell us more about how the length of the campaign effects succes which I believe could be very useful data. That would be a graph that we could add that woudl help Louise understand how time affects kickstarter success.





