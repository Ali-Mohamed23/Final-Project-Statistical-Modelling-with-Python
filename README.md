# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The goals for this project is to utlize the skills I have learned in the first 3 weeks of the Lighthouse Labs Data Science bootcamp. For this project I will be completing the following: 

- Accessing data using APIs
- Cleaning and transforming data using Python
- Loading data into a database using Python
- Performing EDA, including using both statistics and visualizations
- Identifying trends and patterns in data using statistical models
- Interpreting the results of the statistical models


## Process
### Part 1: Connecting to the City Bikes API 

For this step I started by exploring the structure of the API and understanding how all the lists and dictionaries within the dictionary are related in order to be able to filter the results I wish to view. I located the Vancouver network of bikes within and created a query to provide all bike stations in the city with the amount of free bikes available at a moment in time. I was able to get the longitude and latitude of each of these stations and converted the output into a Pandas data frame. 

All of the code for this Part 1 is located inside city_bikes.ipynb that is located within this repository.

### Part 2: Connecting to Foursquare and Yelp API

For this step I was able to pull data from two other API's. I faced a challenge within this step of getting my API query to loop for all of the bike stations in the city bikes data frame that I created. My solution was to get a random sample of bike stations within the dataframe and using their coordinates to make a query for the Foursquare and Yelp API. This was successful however it did not provide a large data set as my sample was only 5 bike stations. I then combined the results of API query to make a combined dataframe that included all 5 bike station queries. The data that I was able to achieve from these API get requests included the nearby restaurants from each of the bike stations, along with their ratings. 

Upon comparison of the Yelp and Forsquare data, I chose to continue with the Yelp API to use in my regression analysis in the next step of this project.

All of the code and results are located inside the Yelp_Foursquare_EDA.ipynb notebook within this repository. 

### Part 3: Joining Data from City Bikes data frame & Yelp dataframe

With the two dataframes I was able to combine both them by using the coordinates of the bike station as the related column. I used the pd.merge function in my notebook which gave me a combined dataset that included the bike station address, coordinates, restaurant, restaurant address, and restaurant rating. I also created visualizations from Matplotlib to further analyze this data which included bar graphs, and regression plots. 

The code for this combined dataframe is included in the joining_data.ipynb notebook in this repository. 

### Part 4: Building a model 

In this last step I used statsmodel.api to create a linear regression model from the combined dataframe. The results were difficult to interpret due to the limited amount of data collected from my API queries. I used the amount of free_bikes as the dependant variable and the bike station and restaurant rating as the independent variables. Although the results indicated a .48 R squared the data cannot be relied upon due to the limit on the sample size. In conclusion, the question which I wanted to answer on whether the variance of free_bikes has a correlation to the ratings of nearby restaurants or location of bike stations could not be answered from this regression model. 

## Results
The results of my data are included in my notebooks along with a powerpoint which has the summary of the results located within this repository. 

## Challenges 
My biggest challenge in this project was creating the loop on my API queries for Yelp and Foursquare. This caused my dataset to be limited to only 5 bike stations which had an effect on my regression results. 

## Future Goals
If i had more time I would have gathered more data from my API requests including more columns such as nearby parks. I also could have completed the API searches at different times in the day as I am sure that has an effect on the amount of bikes available and would be an interesting regression analysis. 
