# Final-Project-Statistical-Modelling-with-Python

## Project Description

This repository consists of an exploratory data analysis project with multiple steps and extensive data collection, visualization and statistical processes. 

The data was collected using CityBikes, which is a bike sharing platform and service venue APIs such as Foursquare and Yelp. 

## Aims 

The main aim of this project was to explore the relationship between bike-sharing usage and how the geographical location of the bike-sharing stations can be optimized in the future based on the characteristics of the amenities around the stations. 

The second aim of the project was to provide the bike-sharing company with information regarding the various categories of venues such as popular restaurants, museums around their bike stations to improve marketing and reach of their company in this region. 

## Process
### Getting Started 

This included: 

1. **Cloning the repository to local machine**: This is the first step to start working on the project locally.

2. **Installing required dependencies**: Using pip install, I installed necessary libraries like numpy, pandas, matplotlib, seaborn, statsmodels, plotly, requests, and sqlite3.

3. **Exploring the APIs**: I brainstormed potential insights that could benefit the business and established project aims.

### APIs

Working with APIs was a challenging yet rewarding step in this project. Despite facing several difficulties, I was able to overcome them by following the documentation and troubleshooting issues. Here are the key steps:

1. **Understanding the APIs**: I read the documentation of each API to understand their endpoints and parameters.

2. **Securing API keys**: I generated API keys for each service and stored them securely.

3. **Implementing API requests**: I used libraries like `requests` to fetch the required data.

4. **Handling authentication and rate limiting**: I followed the API guidelines to manage authentication and rate limiting.

5. **Processing the data**: I processed the retrieved data to extract relevant information for analysis.



### Part 1 : CityBikes API 

1. **Understanding the API**: I delved into the documentation of the CityBikes API to comprehend its structure.

2. **Executing a query**: I executed a query and selected a city near my hometown out of personal curiosity and familiarity.

3. **Parsing JSON responses**: The JSON responses were parsed using specific functions and the data was stored in a Pandas dataframe for further analysis.

4. **Switching the city**: Upon discovering that my initial city lacked YELP coverage, I switched to a historic town in Belgium, Gent.

The entire process is meticulously documented in the Jupyter notebook named 'city_bikes_final.ipynb'. The preliminary file is named 'city_bikes_bhopal.ipnyb'.

### Part 2: Connecting to FourSquare and Yelp APIs

1. **Securing authentication tokens**: I securely stored my authentication tokens and ensured that they were not visible in any part of my code.

2. **Retrieving information**: For each bike station, I used the foursquare and yelp APIs to retrieve information about nearby restaurants, museums, and bars.

3. **Creating functions and dataframes**: I initially created functions querying data for all stations repeatedly then later rewrote them to parse and collect the data first. I created several dataframes for the individual restaurant, bar, and museum data.

4. **Calculating averages and counts**: I calculated averages and counts, and merged this data with the station data to provide a comprehensive view of the Points of Interest (POIs) around the bike stations.

5. **Handling API limitations**: I ran into challenges due to Yelp's different querying process and API call limit, but managed to create two separate dataframes for both services, each containing the same aggregate characteristics. Unfortunately, I was unable to collect the necessary data for my project using the YELP API and proceeded with the analysis using FourSquare Data. 

6. **Conducting comparative analysis**: Lastly, I conducted a comparative analysis of the data received from both APIs and evaluated the quality of the data.

This process is documented in 'yelp_foursquare_eda_final.ipnyb'. 

### Part 3 : Joining Data 

1. **Data Integration**
   - **Merging Data:** CityBikes and Yelp POI data and FourSquare POI data were combined into a unified DataFrame to facilitate comprehensive analysis.
   
2. **Exploratory Data Analysis (EDA)**
   - **Visualization Techniques:** Employed various visualization techniques such as maps, scatter plots, and heatmaps to identify and illustrate patterns and insights from the combined dataset.
   
3. **Database Creation**
   - **SQLite Database:** Developed a SQLite database with a thoughtfully designed schema to efficiently store and manage the merged data.
   - **Data Integrity:** Implemented measures to ensure data integrity, including data validation and consistency checks.
   
4. **Documentation**
   - **Detailed Jupyter Notebook:** All processes, from data merging to EDA and database management, are meticulously documented in the Jupyter notebook `joining_data.ipynb`.

For a detailed walkthrough of the analysis and findings, refer to the Jupyter notebook 'joining_data_submission_1.ipynb' included in this repository.

### Part 4 : Model Building 

This part focused on building and analyzing statistical models to understand the relationship between bike station dynamics and surrounding Points of Interest (POIs) using Python’s statsmodels module.

Key components of this project include:

1. **Regression Modeling**
   - **Model Development:** Developed a regression model to explore the relationship between nearby POIs on the number of bikes available at each CityBikes station.
   - **Model Interpretation:** Analyzed and interpreted the results to extract actionable insights about the influence of POIs on bike station performance.

2. **Problem Transformation**
   - Explored how the regression problem could be transformed into a classification problem, including outlining potential methodological approaches without actual implementation.
   
3. **Documentation**
   -  Detailed all methodologies, from model construction through to interpretation and conceptual transformation, in the Jupyter notebook `model_building.ipynb`.


## Results

For the city of Bhopal that I initially picked, the foursquare results were sparse yet existed. For Yelp, there was no data present. Therefore, the 'coverage' of Yelp in that sense is limited to very few countries and it would be better to use FourSquare for a more global approach. 

For the city of Gent that I later picked, Yelp had many more rows of data and more comprehensive coverage around the area. As the city is densely packed, it did involve a lot more data preprocessing before the analysis for the Yelp data for this city. However, foursquare also provided important insights regarding the characteristics of the POIs. Yelp also had more information in terms of location, contact information, review_counts along with the rating which was important for the analysis. A key advantage of the foursquare data, however, was the popularity parameter. This is key as it examined the foot traffic around POIs for a 6-month period since the data collection, and I believe that is crucial to the analysis for how a bike-sharing platform can use information from venues around the stations to enhance its usage and improve outcomes. 

## Challenges 
### Data Collection Challenges

This section outlines the significant challenges faced during data collection from Yelp and CityBik.es APIs and how these might impact the scope and depth of the analysis.

1. **Yelp API Limitations**
   - **Daily API Call Limits:** The restrictive daily limits on API calls to Yelp pose a significant challenge in gathering data efficiently, particularly for larger datasets. This slows down the process of data collection, affecting the overall project timeline.
   - **Results Per Call Limit:** Each API call to Yelp returns a maximum of 50 results. For analyses that require data within a radius of 1000 meters, this limit could potentially exclude many relevant businesses, thereby constraining the breadth and depth of the analysis.

2. **CityBik.es Dataset Dynamics**
   - **High Data Dynamism:** The CityBik.es dataset is highly dynamic with bikes being rented and returned frequently throughout the day. This constant fluctuation requires careful consideration in data handling and analysis to accurately reflect usage patterns and station activity over time.

3. **Parsing JSON**
    It was diffult to determine what to exactly extract from comprehensive JSONs provided by the tw venue APIs. It took a long time to fix the formatting of the data types extracted, especially for the categories in Yelp data. 

### Data Visualization 

It was challenging to pick the right visualization techniques that condensed a large amount of information into one plot. Aggregation of data has its pros and cons and it was challenging to conceptualize the findings based on just aggregate data. 


## Future Goals


1. **Feature Selection Refinement**
   - Dedicate more time to selecting the most relevant features for the regression model to ensure it accurately captures the essential variables influencing bike station dynamics.

2. **Data Enrichment**
   - Explore deeper into Yelp and Foursquare datasets to extract additional numerical data that could further refine and tune the regression model.
   - **Broaden Data Sources:** Investigate data from other bike-sharing platforms to enhance the model’s comprehensiveness and comparative analysis capabilities.

3. **Code Optimization**
   - Review and refine the existing code in the notebooks to enhance efficiency. Better utilization of functions and modular coding practices could streamline the analysis process.

4. **Data Cleaning**
   - Increase focus on data cleaning to ensure the quality and reliability of the data used in the models. A more thorough preprocessing stage is crucial for accurate model performance.

5. **Goal-Oriented Analysis**
   - Start with a clear definition of the project goals, especially for the later stages of the model development. Work backward to align all preparatory steps with these objectives to ensure coherence and relevance of the data analysis.

6. **Data Collection Adjustments**
   - Address limitations in data collection by:
     - Collecting missing data from Yelp for stations where the API's results limit has been reached.
     - Utilizing Foursquare’s less restrictive API to identify and integrate the most correlated attributes which can complement the Yelp data.
     - Implementing more frequent data pulls from City Bik.es to capture dynamic changes over time, potentially scheduling multiple data retrieval sessions daily or weekly.


By addressing these challenges and implementing the suggested enhancements, the project can significantly improve in terms of data quality, model accuracy, and insight depth.
