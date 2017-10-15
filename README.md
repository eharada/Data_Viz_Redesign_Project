# Data Redesign Project: Does location play a role in mental health policies in companies?

## Project Statement:

For this project I wanted to focus on the healthcare industry and more specifically healthcare and technology. Although mental health has been around for decades, is a newly dicussed topic especially in Silicon Valley. The data set was pulled from Kaggle.com, which pulls in survey data for how comfortable people feel with being open with their mental health in the technoogy workplace.

https://www.kaggle.com/osmi/mental-health-in-tech-survey

The data visualization that Kaggle user, Lislejoem, created focuses more on bar charts that show the difference between yes/no questions. He focuses more on the difference in opinion between those who have reached out for support and those who have not. 

https://www.kaggle.com/lislejoem/recognition-of-importance-of-mental-health-in-us

The majority of Lislejoem's visuals are bar chart that measure the number of responses.

![image](https://user-images.githubusercontent.com/32119820/31578091-2ce598f0-b0cf-11e7-8fd2-6638281815f5.png)


I would like to take the same data and add geography in the equation. My goal is to see if there is more openness to mental health in certain states and if that is related to how much people perceive it to interfere with their work. 

---------
## Project Progression:
<b> 1st Step: Explore Data </b>
First I started with my exploratory visual with the current data that I had. I wanted to get a clear picture of what was possible and if there was any correlation that I was missing from just looking at the spreadsheet. With that, I created these visuals that show which states have the highest number of tech employees who feel that their mental health interferes with their work as well as the number of companies who don't offer or don't make it clear that they have wellness programs.

![image](https://user-images.githubusercontent.com/32119820/31318365-d42c4704-ac05-11e7-8077-cebd042b10a4.png)
![image](https://user-images.githubusercontent.com/32119820/31318370-e86b5bf6-ac05-11e7-98e0-5af3e34c2034.png)

The above graphs depict California as being the top state in which tech employees believe their mental health interferes with their work. It is also the top state in which employees aren't sure if their employers offers wellness programs.

<b> 2nd Step: Data Wrangling </b>
My next step was data wrangling. I had to clean up the spreadsheet as there were a lot of fields that were free text rather than a drop-down. For example, the Gender column allowed a free form text which caused many variations of Female (i.e. Female, Woman, Female CIS). I was able to convert the Gender column to Female and Male. I also wanted to exclude any rows that had blank answers for work interference since we are trying to see if there is a correlation between work intereference and wellness programs. If we had left in the blanks, then that would skew our data because we would have more responded for wellness programs than work intereference. I was able to use the following website on help with the re library and regular expressions.

https://docs.python.org/2/library/re.html


<b> 3rd Step: Data Visualization Prototypes</b>

<b><i> First Iteration- </b></i><br/>

![image](https://user-images.githubusercontent.com/32119820/31402175-14ee64fc-adaa-11e7-98f5-fb268d556b61.png)

In the first iteration I assumed that the response rate for each state is the same. Therefore the comparison would be equivalent and we could easily see which states had a higher average of work intereference and employees feeling lack of support from their companies. However this was not the case and California had the highest number of responses, which could be due to having more tech companies in that state.
<br/>
In the next version, I will remove the states with low response rates (Ex: Idaho had 1 response) and I will normalize the data to show the responses per size of population. This will allow us to compare apples to apples in terms of population size.
<br/><br/>

Advantage: This chart shows how the states with the highest number of tech employees are unsure or know that their company does not offer wellness programs. Employees feel that mental health is a burden as there is not support system in place at these tech companies.
<br/>
Disadvantage: This chart had to be manually sorted from highest to lowest average of work intereference. In addition it might be easier to visualize this through a map or a trendline to see if there is a stronger correlation between work interference and lack of mental health programs.
<br/><br/>

<b><i> Second Iteration- </b></i><br/>
For this iteration, I cleaned up the data to exclude the states that had less than 10 responses for those were in tech companies as this skews the data. The below states will be excluded from all future data visuals.

![image](https://user-images.githubusercontent.com/32119820/31580254-00e8074e-b0ff-11e7-8565-dab9317297b8.png)

In addition, I updated the Jupyter Notebook to include a spreadsheet of the US populations per year. The original spreadsheet was taken from census.gov and showed each US state and territory's population from 2010-2016. However we are only interested in 2014 as that is when the survey was submitted. With the 2014 population, we can now normalize the data and compare apples to apples by dividing the response rate by the population per state. This will allow us to see what percentage of the entire population feels that work interferes with their work and if they feel support from their work. 





-------------------------
1. Project statement (Motivation, objective, data, project plan)
2. “Making-of” documentation (Details of your development process, data wrangling steps, your reasoning,
detours, literature, etc.)
3. Several intermediate visualization prototypes
4. Final data visualization
5. Road map with future features/enhancements/features
6. Showcase video (<90 sec)
