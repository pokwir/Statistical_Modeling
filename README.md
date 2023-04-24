# Final-Project-Statistical-Modelling-with-Python
---

## The goal of this project is to access data using APIs, clean, transform, load, perform EDA, and identify trends and or patterns using statistical models with Python.

## Process
---
### Accessing Data using APIs.
- City selected. Portland, Oregon.
- initial reconnaissance of the structure of the APIs (City Bike, Yelp, and Foursquare), was done. A get request was sent for each API to understand the structure of the data returned.
- APIs were queried and the response json files were parsed to create and Pandas DataFrame. Each DataFrame was cleaned and transformed in python before exporting to csvs for storage.
- Using sqlite3, the data was loaded into a sqlite3 database using Python.
- Exploratory Data Analysis (EDA) was using both statistics and visualizations. Trends and patterns in data were identified using statistical models. I used a combination of pandas, seaborn, matplotlib and [ydata_profiling](https://pypi.org/project/pandas-profiling/) which was handy and very useful, it summarizes the dataset into a one-page html — speeding up the EDA process and providing a reference I can quickly visualize.
- A linear regression model was made to investigate the relationship between reviews of a POI and number of bikes.
- An interpretation of the results was documented.

## Results
---


Overall the Yelp API is well documented, rich - more POIs, complete (no missing data for parameters queried per POI). This is especially important depending on the use case of the data. If further analysis is going to be done like conducting regression modelling, rich data is important and having to drop/ fill for a large number of observations is taxing and reduce overall quality of the model.

![Correlation Heatmap](https://github.com/pokwir/Statistical_Modeling/blob/main/images/Correlation_Heatmap.png)

My model could only explain 5.7% (R-squared 0.057) of the patterns in the data. This is not surprising because the correlation between number of bikes at a location and reviews of the POI was only 0.23 even after normalization. Number of reviews does affect number of bikes at a particular location. A unit increase in reviews will have a positive impact on number of bikes at a location.

![Correlation Model](https://github.com/pokwir/Statistical_Modeling/blob/main/images/Regression_Model.png)


## Challenges
---
1. Connecting to the APIs was time consuming - documentation was confusing and each had its own method of authentication. .
2. Joining the DataFrames from part 1 and 2. Instruction was a little confusing because part two had two DataFrames both with different measurement variables. Example Yelp uses number of reviews and foursquare has a popularity score.
3. EDA. Bike station related variables had strong correlation each other, but POI variables like reviews, price, category had very little (correlation 0.02) or none. To build a regression on this was a challenge. I had to do transformation and normalization because all the variables were not normally distributed.

## Future Goals
---
Chose multiple cities to get a diverse range of data but also a better sample in terms of depth and size.
