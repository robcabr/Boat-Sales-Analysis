# Boat-Sales-Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Context](#context)
- [Tools and Techniques](#tools-and-techniques)
- [Summary of Techniques Employed](#summary-of-techniques-employed)
- [Project Goals](#project-goals)
- [Key Questions](#key-questions)
- [Stakeholders](#stakeholders)
- [Tableau Story](#tableau-story)
- [Data Source](#data-source)
- [Preprocessing the Data](#preprocessing-the-data)
- [Summarizing and Analyzing Data](#summarizing-and-analyzing-data)
  - [Introduction Analysis](#introduction-analysis)
  - [Exploratory Analysis](#exploratory-analysis)
  - [Testing New Hypotheses](#testing-new-hypotheses)
  - [Cluster Analysis](#cluster-analysis)
  - [Further Cluster Visualizations](#further-cluster-visualizations)
  - [Key Questions Answers](#key-questions-answers)
- [Conclusion](#conclusion)

## Project Overview
In this exploratory project, our goal is to identify key factors that can contribute to a boat listing's success in terms of views. This repository dives into the analysis of boat sales data, focusing on market trends and consumer behavior. The analysis employs exploratory data analysis, visual analysis conducted in Python, hypothesis development, and the application of advanced analytical techniques, such as linear regresssion and k-means clustering, built up to a visual presentation done in Tableau. 

## Context
For this project, I utilized a dataset sourced from [Kaggle](https://www.kaggle.com/datasets/karthikbhandary2/boat-sales?resource=download). The exploratory visual analysis was conducted in Python to identify correlations between variables, leading to deeper exploration. Based on these connections, hypotheses were formulated and tested using advanced analytical methods. Finally, a storyboard in Tableau will present the results of these tests.

## Tools and Techniques
I utilized Python along with the following libraries:
- **NumPy**: For numerical operations.
- **Pandas**: For data manipulation and analysis.
- **Scikit-learn**: For implementing machine learning algorithms.
- **Matplotlib and Seaborn**: For creating visualizations.
- **Tableau Public**: For presenting results visually.

### Summary of Techniques Employed
- **Data Wrangling**: Cleaning, transforming, and organizing raw data into a usable format, to ensure that it's ready for analysis.
- **Data Cleaning and Summarization**: Correcting or removing errors to maintain data quality, as well as summarizing insights or key information for clarity purposes.
- **Correlation Analysis**: Identifying relationships between variables, as well as its strength, to identify potential correlations.
- **Linear Regression**: Analyzing the impact of continuous variables on view counts.
- **K-means Clustering**: Grouping data points to identify patterns.

## Project Goals
1. Identify successful boat listings based on view counts.
2. Determine factors that contribute to a listing's visibility.
3. Explore pricing patterns related to boat age and material.

## Key Questions
- **Which countries have the highest view counts, and how does this relate to pricing?**
- **What is the relationship between the year built and the number of views?**
- **How does price correlate with views in the boat listings?**
- **Are there distinct patterns in views based on boat material?**

## Stakeholders
- **Boat Consumers**

## Tableau Story
I have compiled the most significant visualization into a Tableau story to facilitate understanding for stakeholders. You can explore the visual narrative through my [Tableau Link](https://public.tableau.com/app/profile/robson.tadeu/viz/BoatSalesAnalysis-1900to2021_/Story1)
  
## Data Source
The dataset used in this project is sourced from an external repository that compiles boat sales data and can be found in the following link [Kaggle](https://www.kaggle.com/datasets/karthikbhandary2/boat-sales?resource=download).

## Preprocessing the Data
Before proceeding to analysis the dataset went through several preprocessing steps:

1. Explored the shape of the data frame, column data types, and summary statistics of numerical columns.
2. Performed data wrangling, including renaming columns and dropping unnecessary ones.
3. Checked data for consistency, addressing mixed data types, duplicates, and missing values.
4. Calculated summary statistics post-consistency check and removed outliers.

## Summarizing and Analyzing Data

### Introduction Analysis
I began my analysis with exploratory data analysis, focusing on the distribution of views by country and price.

<p align="center"> <img width="80%" alt="map visualization showing aggregation paramethers" src="https://github.com/robcabr/Boat-Sales-Analysis/blob/main/Visualization/1%20-%20Introduction%20-%20Map%20Visualization.png"></p>

*As can be seen above, Switzerland leads in weekly views, accounting for a significant portion of the total dataset, around 30% by itself. On the other hand, the top five countries generate almost 80% of the total views, indicating a concentration of interest in specific regions. This finding suggests that marketing strategies could be tailored to these countries.*

### Exploratory Analysis
Next, I examined the relationship between views and price through scatterplots, hypothesizing that higher-priced boats would attract more views.

<p align="center"> <img width="80%" alt="Scatterplot - Relationship between price and views" src="https://github.com/robcabr/Boat-Sales-Analysis/blob/main/Visualization/2%20-%20Exploratory%20Analysis%20-%20Price%20X%20Views.png"></p>

*The scatterplot revealed no significant correlation between price and views, suggesting that high-priced boats do not necessarily attract more interest. This challenges the assumption that pricing directly influences visibility.*

### Testing New Hypothesis

Continuing with my exploration, I analyzed views by year built, hypothesizing that newer boats would attract more views. A linear regression trend was applied to explore this hypothesis, to evaluate if any trend could be observed.

<p align="center"> <img width="80%" alt="Scatterplot - Relationship between year built and views" src="https://github.com/robcabr/Boat-Sales-Analysis/blob/main/Visualization/3.1.%20-%20Views%20by%20Year%20Built.png"></p>
<p align="center"> <img width="80%" alt="Bar plot - total of views by year built" src="https://github.com/robcabr/Boat-Sales-Analysis/blob/main/Visualization/3.2.%20-%20Views%20by%20Year%20Built.png"></p>

**The analysis concluded that there was no trend or correlation between the year built and views, indicating a complex relationship, since, altought in some situations, older boats received more views than newer models, the number of views increase as the year built increase, suggesting that further analysis is necessary to understand consumers preference.*

### Cluster Analysis
Since Linear regression was not enough for validate any of our hypothesis, as there is no clear trend between the variabels Price or Year Built with the number of views, a non-linear approach is necessary, to uncover patterns among the variables Views, Price Amount and Year Built. So, I applied k-means clustering, revealing distinc groupings. 

This analysis identified the following distinct segments (clusters):

* Segment first (Cluster 1): Comprised newer boats, most from 1980 onwards (except for one from 1960), as well as the most expensive ones.
* Segment second (Cluster 2): Contained boats from various years, including the cheapest ones, priced below 1 million.
* Segment third (Cluster 3): Featured boats around 2 million, most of which were built from 1980 onwards.
* Segment fourth (Cluster 4): Included boats starting from 1920, with most from 1960 onwards, and most priced below 2 million.

<p align="center"> <img width="80%" alt="Scatterplot - Cluster applied to identify relationship between variables Views and Price/Year Built" src="https://github.com/robcabr/Boat-Sales-Analysis/blob/main/Visualization/4%20-%20Cluster%20Analysis.png"></p>

*Although the analysis was able to revealed distinct groupings, with clusters indicating varying characteristics related to price and views, further analysis was necessary before any conclusion could be done, so I proceed with some other analysis, as can be seen below.*

### Further Cluster Visualizations 
So, after clustering the data, some additional visualizations were created:
1. A scatter plot showing total views from the last 7 days by material and cluster.
2. A bar chart illustrating total views by segment.
3. Data points demonstrating the count of views by materials.


<p align="center"> <img width="80%" alt="Scatterplot - Cluster applied to identify relationship between variables Views and Price/Year Built" src="https://github.com/robcabr/Boat-Sales-Analysis/blob/main/Visualization/5%20-%20Cluster%20Results.png"></p>

*These results provide insights into how materials and prices influence consumer views. Notably, segments reveal varying characteristics that could guide inventory and pricing strategies.*

The results of the clustering revealed the following insights:

* Segment Second (Cluster 2) has the highest average number of visits per week at 423.2 and the second highest total number of visits (379,571). This aligns with its low average price of $44,470 and total price of $39,889,695. Most of its boats are from 1981 onwards and are made primarily from GRP and wood, which likely appeals to its audience.
* Segment Third (Cluster 3) has the highest total number of views at 388,337 and the second highest average number of views per week at 137.3. This can be connected to its average price of $86,949 and a total price of $245,891,431. This segment includes boats from all year groups but is most dominant from 1960 onwards, featuring a significant concentration of GRP and PVC boats.
Although a connection was found between the two segments with the highest views per week and their respective prices, this trend does not hold for the other segments:
* Segment First (Cluster 1), with the highest average price of $3,616,186, total price of $ 885,965, 557, has an average of 127.6 views and total of 31,274 per week. This segment predominantly features GRP and PVC boats.
* Segment Fourth (Cluster 4), with an average price of $348,464 and a total value of $918,900,866, should logically yield lower views compared to the First Segment. While it is true that the average views are lower by nearly 25, the difference in total views is around 240,000, despite having a higher total price. The material distribution in this segment includes a mix of GRP, PVC, and steel.

### Key Questions Answers

1. **Which countries have the highest view counts, and how does this relate to pricing?**
   - The analysis revealed that Switzerland accounts for approximately 30% of total views, with the top five countries generating nearly 80%. This concentration suggests a strong market presence in specific regions. After further understand how each variables affects the weekly views, trends could be explored further later.

2. **What is the relationship between the year built and the number of views?**
   - The analysis indicated no clear correlation between the age of boats and view counts. While newer boats might be expected to attract more views, historical data showed that older models occasionally outperformed newer ones in terms of views.

3. **How does price correlate with views in the boat listings?**
   - Initial expectations that higher-priced boats would attract more views were not supported by the data. The scatterplot analysis revealed no significant correlation between price and views, indicating that consumers may prioritize other factors over price alone.

4. **Are there distinct patterns in views based on boat material?**
   - The clustering analysis revealed distinct consumer segments based on boat material preferences. For instance, Segment 2 demonstrated the highest average views with boats primarily made from GRP and wood, indicating a preference for these materials, which could be connect to their perceived quality and value.
   

## Conclusion

Based on the finding above explained, it is possible to evaluate that price and materials influence consumer views per week, but the relationships are complex and may not follow straightforward patterns, so no conclusion can be done in the moment about what directly influences the number of views weekly.

To sum up, the complex interplay between price, material, and consumer preferences suggests that further analysis is necessary to fully understand these relationships. Utilizing advanced techniques such as multivariate regression analysis could provide deeper insights into how multiple factors influence views simultaneously.
