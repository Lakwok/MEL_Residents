# MEL_Residents 
### See the project output in ShinyApp: https://lakwok.shinyapps.io/the_resident_demographic_in_the_city_of_melbourne/
### The goal of project  

This project mainly focuses on the demographic topic to the residents living in the City of Melbourne in census 2011 and 2016, but also slightly reaching the economy, employment and education topic.  
Task 1: What is the population of each suburbs in the City of Melbourne in 2016 and what is difference compared with 2011?  
(For Task 1, code and explaination can be found in the page Population).  

Task 2: What is the percentage of four key groups between the City of Melbourne and Greater Melbourne in census 2011 and 2016?  
Task 3: How does the percentage changes over year in the City of Melbourne? Is it similar to the changes in Greater Melbourne?  
Task 4: What is the proportion of each five year age group in the City of Melbourne in 2016. Is it similar to Greater Melbourne?  
Task 5: What is population and age pattern  among the different suburbs in teh City of Melbourne, and what is noteworthy compared with 2011 in 2016?  
(For Task 2 to 5, code and explaination can be found in the page Age and relevant tabset)

Task 6: What languages the residents in the City of Melbourne speak at home besides English? 
(For Task 6, code and explaination can be found in the page Language)

Task 7: What is the number of students in different education types in different suburbs? Which regions has the most and least university students?  
(For Task 7, code and explaination can be found in the page Student)

Task 8: What is the main types of occupations in the City of Melbourne? Will the main occupations in CBD be different?
(For Task 8, code and explaination can be found in the page Occupation)

Task 9: What is the median income in each suburbs? How does it differ among suburbs over years?
(For Task 9, code and explaination can be found in the page Income)

Task 10: Creating a model to evaluate the correlation between median income and education level, occupation type and year among the factors of geography, year, rental payment mean, education level, median income, age median and occupation type.
(For Task 10, code and explaination can be found in the page Model)  


### How to run the analysis  

Task 1: The raw data does not provide the population for each suburbs, so I focus on the value of key age groups which have only four group for the age unlike the other detail range groups. After filtering the key group data and clean it , I can calculate the sum of the value of each key group.  

Task 2: In the task 1, I pivot four key groups in the variables for population but I can not use the population in that dataset for computing the percantage(Computing the percentage in that dataset would be mess). I keep the four key groups in the same column and groub by the geography(City of Melbourne and Greater Melbourne) and year, then I do some percentage calculation to get the answer.  

Task 3: I have already get the percentage of each key groups so I use the 'lag()' to get the previous value for particular key group and compute the percentage change for each key group. It's luckily that lag function also appeared in the pratical exam.  

Task 4: To get the proportion of each 5 year range groups is similar to what I did in the task 2. However, to give the audience with an effective visualization is important cause there are 20 ranges in the plot. Population pyramid may be a good one to show the ranges so I work it on the ggplot and successfully constructing the figure.  

Task 5: In the final age part, I construct a big 100% chart to show the population change in each 5 year range group and each suburbs.  

Task 6: For answering this question, I selecet the language data that hase been tidied at first. There are over 33 languages in this dataset, to plot this, the treemap may be a good choice so I install the 'treemapify' package to allow me using the treemap in the ggplot.  

Task 7: Filtering the suburbs in th City of Melbourne and adjusting the legend format by using case_when for the theme_economist, then plot the 100% chart for it by ggplotly.  

Task 8: Filtering the geography to the City of Melbourne and reorder the occupation by value in the plot.  

Task 9: Filtering the City of Melbourne and plot the data that hase been tidied at first.  

Task 10: To obtain the model data, we still need to select a value for rent. However, the value of retal payment is a rang value so I firstly separate the range into lower and upper. Then, Calculating the median for these two columns and applying function 'weighted.mean' to calculate the weighted arithmetic mean for rental payment by weighting the persons in each range level.Further, I can bulid the linear model and add the specific variables to the formula. 
