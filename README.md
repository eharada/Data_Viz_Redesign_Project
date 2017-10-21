# Data Redesign Project: Does location play a role in mental health policies in companies?

## Project Statement:

For this project I wanted to focus on the healthcare industry and more specifically healthcare and technology. Although mental health has been around for decades, is a newly dicussed topic especially in Silicon Valley. As this becomes a bigger buzz word, companies should be cognizant of how mental well-being plays a role in their company's success and potentially alter their benefits. The data set was pulled from Kaggle.com, which has survey data for how comfortable people feel with being open with their mental health in the technoogy workplace and how supported they feel by their employers.

https://www.kaggle.com/osmi/mental-health-in-tech-survey

The data visualization that Kaggle user, Lislejoem, created focuses more on bar charts that show the difference between yes/no questions. He focuses more on the difference in opinion between those who have reached out for support and those who have not. His motivation for this is to see there is a clear understanding of the importance of mental health.

https://www.kaggle.com/lislejoem/recognition-of-importance-of-mental-health-in-us

The majority of Lislejoem's visuals are bar charts that measure the number of responses.

![image](https://user-images.githubusercontent.com/32119820/31578091-2ce598f0-b0cf-11e7-8fd2-6638281815f5.png)


However often times there are many different factors, so I would like to take the same data and add location in the equation. My goal is to see if there is more support for mental well-being in certain states and if that is related to how much people perceive it to interfere with their work. 

---------
## Project Progression:
<b> 1st Step: Explore Data </b>
First I started with my exploratory visual with the current data that I had. I wanted to get a clear picture of what was possible and if there was any correlation that I was missing from just looking at the spreadsheet. With that, I created these visuals that show which states have the highest number of tech employees who feel that their mental health interferes with their work as well as the number of companies who don't offer or don't make it clear that they have wellness programs.

![image](https://user-images.githubusercontent.com/32119820/31318365-d42c4704-ac05-11e7-8077-cebd042b10a4.png)
![image](https://user-images.githubusercontent.com/32119820/31318370-e86b5bf6-ac05-11e7-98e0-5af3e34c2034.png)

The above graphs depict California as being the top state in which tech employees believe their mental health interferes with their work. It is also the top state in which employees aren't sure if their employers offers wellness programs.

<b> 2nd Step: Data Wrangling </b>
My next step was data wrangling. I had to clean up the spreadsheet as there were a lot of fields that were free text rather than a drop-down. For example, the gender column allowed free-form text which caused many variations of Female (i.e. Female, Woman, Female CIS). I was able to convert the gender column to Female and Male. I also wanted to exclude any rows that had blank answers for work interference since we are trying to see if there is a correlation between work intereference and wellness programs. If we had left in the blank responses, then that would skew our data because we would have more responded for wellness programs than work intereference. I was able to use the following website to get help on using the re library and regular expressions.

https://docs.python.org/2/library/re.html


<b> 3rd Step: Data Visualization Prototypes</b>

<b><i> First Iteration- </b></i><br/>

![image](https://user-images.githubusercontent.com/32119820/31402175-14ee64fc-adaa-11e7-98f5-fb268d556b61.png)

In the first iteration I assumed that the response rate for each state is the same. Therefore the comparison would be equivalent and we could easily see which states had a higher average of work intereference and employees feeling lack of support from their companies. However this was not the case and California had the highest number of responses, which could be due to having more tech companies in that state. This skewed the data, which led to California being perceived to be the state with the highest lack of support.
<br/>
In the next version, I am going to normalize the data to show the responses per size of population and remove the states with low response rates (Ex: Idaho had 1 response). This will allow us to compare apples to apples in terms of population size.
<br/><br/>

Advantage: This chart shows the states with the highest number of tech employees who are unsure or know that their company does not offer wellness programs. Employees feel that mental health is a burden as there is no support system in place at these tech companies.
<br/>
Disadvantage: This chart had to be manually sorted from highest to lowest average of work intereference. In addition it might be easier to visualize this through a map or a trendline to see if there is a stronger correlation between work interference and lack of mental health programs.
<br/><br/>

<b><i> Second Iteration- </b></i><br/>
For this iteration, I cleaned up the data to exclude the states that had less than 10 responses for those were in tech companies as this skews the data. The below states will be excluded from all future data visuals.

![image](https://user-images.githubusercontent.com/32119820/31580254-00e8074e-b0ff-11e7-8565-dab9317297b8.png)

In addition, I updated the Jupyter Notebook to include a spreadsheet of the US populations per year. The original spreadsheet was taken from census.gov and showed each US state and territory's population from 2010-2016. However we are only interested in 2014 as that is when the survey was submitted. With the 2014 population, we can now normalize the data and equally compare the states by dividing the response rate by the population. This will allow us to see what percentage of the entire population feels that work interferes with their work and if they feel support from their work. 
<br/>

For the next iteration, I am going to focus more on the wellness program to see if there is a huge difference between employees who feel they are supported versus those who are unsure or don't feel supported by their employers. I'm going to bring in the state and wellness program responses.
<br/>

Here we can see a side by side comparison between the positive and negative support. Oregon has the highest variance amongst the other 9 states, while California has the smallest difference. This is opposite of what we saw in the initial exploratory data. We saw a map with California having the highest amount of uncertainty on wellness programs. This shows us the importance of normalizing the data so that we don't make false assumptions, which leads to skewed results.

![image](https://user-images.githubusercontent.com/32119820/31580406-b0b89a9a-b103-11e7-9f7d-ec48619e6ee7.png)

Our next step now is to find the difference between the positive and negative support and present that in a United States map (similar to how the exploratory data was shown). This visual will be shown so that those with the highest differences will be in a darker red.

<b><i> Third Iteration- </b></i><br/>
The first step is to create a bar graph that shows the difference between the most and least amount of mental health support per state. This will help us visually see which states have the highest gap between positive and negative support. In the past iterations, we could see that generally there is a higher number of negative support. In this version, we can see that Oregon has the highest difference between the tech companies that offer wellness programs and those who do not/are unsure.

![image](https://user-images.githubusercontent.com/32119820/31677991-88628b3a-b321-11e7-95e3-fa2e978f6e1d.png)

The next step is to plot the data on a map to see which states have the largest variance in mental health support. With the next version, I want to only focus on if the employees know if there is a wellness program. This will make it easier for the audience to quickly see which states will need to take action. 

-------------
## Final Version:

![image](https://user-images.githubusercontent.com/32119820/31678150-0cea0964-b322-11e7-9694-4daa967a01fe.png)

In the above map, the darker colors mean that those states have the biggest gap between high and low support. We can see that Oregon is the darkest color, while its neighboring states, Washington and California, are on the lighter end. Oregon has the biggest variance which shows that employees are very unsure of wellness programs. Meanwhile Washington and California have roughly an even amount of employees who are feel supported versus those who are unsure. California has more than triple the population size than Oregon but is still able to maintain more balance for mental health support. 

It will a good idea for tech companies in Oregon to learn from California and Washington to see how they set up their mental wellness benefits. Oregon should then implement similar programs so that they can attract more employees to their state. Although the Bay Area is a popular destination for many employees, Oregon could potentially be on the same playing field if they are able to offer more variety in their benefits. Mental health will continue to be a growing topic, so future employees will appreciate the tech company's efforts to support their well-being.
<br/><br/>

-----------
## Roadmap:

Future Enhancements: <br/>
1. Get data on a county level to see if certain counties in California differ from each other. Does Silicon Valley offer more wellness programs than the more rural areas?
2. Get data for specific companies/industries to see if mental health support differs between more technological companies.
3. Compare age to see if the younger generation feels more comfortable speaking up about their mental health concerns. Does the younger generation demand more, which leads to more changes in companies?
