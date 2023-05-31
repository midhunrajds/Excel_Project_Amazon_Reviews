
# Data Analysis Project using Excel – Amazon Reviews India

## Abstract
The primary intention is to get an insight into the product reviews on amazon and lookout for any interesting patterns that may help in better product placing and strategy for a potential seller. 

## Introduction
The dataset used in this analysis is the data of 1K+ Amazon Product's Ratings and Reviews as per their details listed on the official website of Amazon. The dataset was obtained from Kaggle.com.
Link to the dataset:
https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset
This dataset is licensed under a Creative Commons Attribution 4.0 International (CC BY-NC-SA 4.0) license.
This allows for the sharing and adaptation of the datasets for any purpose, provided that the appropriate credit is given.


## Context/ Problem
This dataset consists more than 1000 of real products with their identification number listed in the Amazon marketplace. Aim of the project is to gain some insights on the review and rating patterns, identify top performing segments and brands on amazon India and to identify any interesting correlations between the features.



## Purpose of the Study
The project will help to gain knowledge on applying various techniques and tools learnt, to solve data science problems. 
The outcome of the project will help to gain more insights into rating and review patterns. 
On an organizational level, better placement of strategies to increase sales and optimize online experience for customers. 




## Project Description

Various data analytics techniques is applied to explore the data. 
Followed the CRISP-DM process to ensure proper methodology. 
Data Preparation: This raw dataset has missing values and is highly unorganized. I intend to fix the issues by using appropriate methods like imputation and removal. 
Most of the attributes are relevant to the analysis.
Dataset has 1465 sessions and 16 columns in the original csv format.
The file was converted to xls for ease of use and to enable compatibility.

![original csv file](/assets/images/raw.png)


Features
•	product_id - Product ID
•	product_name - Name of the Product
•	category - Category of the Product
•	discounted_price - Discounted Price of the Product
•	actual_price - Actual Price of the Product
•	discount_percentage - Percentage of Discount for the Product
•	rating - Rating of the Product
•	rating_count - Number of people who voted for the Amazon rating
•	about_product - Description about the Product
•	user_id - ID of the user who wrote review for the Product
•	user_name - Name of the user who wrote review for the Product
•	review_id - ID of the user review
•	review_title - Short review
•	review_content - Long review
•	img_link - Image Link of the Product
•	product_link - Official Website Link of the Product

## Data Cleaning Process:

Features discounted_price, actual_price, discount_percentage, rating, rating_count were converted to numerical datatype for analysis purpose. Further cleaning was required as excel was not identifying the currency symbol for the prices. Data cleaning steps done on the numerical data columns:
discounted_price – datatype converted to number. This is a ratio level data.
actual_price – same as above.
discount_percentage – float value between 0 and 1. 
A new column (discount_bracket) created by converting the values to segments based on discount brackets for easier analysis. Using nested IF statements.
Rating – Rank order data/ ordinal datatype similar to Likert scale. There was one null field. The same was replaced with the MODE of the column which was 4.1. 
Ratings ranged from 2 to 5, 2 being lowest and 5 highest review rating received. 
A new column (rating bracket) was created to convert the ratings into segments similar to poor, average, good and excellent. (Nested IF statements)
Rating_count – number value, quantifiable.

The rest of the features were categorical datatype, and for the purpose of my analysis, I will be using the below features from the remaining –
product_id – String text. Nominal Data
product_name – A long string with the brand name at the beginning, Used the =LEFT function to extract the brand name and placed on a new column. (brand). The brand column had some ambiguous data with same some typo errors and mismatches caused due to spacings, the same was fixed by using =PROPER and =TRIM functions, and Find & Replace functions as required. Eg: Amazonbasics and Amazon Basics were the same brand but identified as different on filters because of typo.
category – a long string with category and subcategory separated by “|”. Used the text to column function to split the string and created new columns for category, and subcategories. As some of the newly created columns had a lot of null values and were repetitive in nature, only a category and subcategory were retained. The missing values in the subcategory were replaced with “Misc” for null values.
The rest of the categorical features were not of much use for the exploratory purpose using excel, as they were lengthy strings with no strict datatype followed (user_id, review description etc) so they were discarded. 

## Exploratory Data Analysis:

### Manage missing data and outliers:
There was one null field in rating. The same was replaced with the MODE of the column which was 4.1. 
Unusually large review counts were found for some products but they would probably be not an error but can be considered as an outlier as they were for products sold directly by Amazon basics. 
Data normalization can be done for these numbers using z_score or max-min normalization if required. 

### Key insights visualizations:
The cleaned dataset was converted to a table, and pivot tables were inserted to explore relations and create graphs and 2-D stacked columns.

### Validation
During the data validation phase of the Excel project, checks were done to ensure the accuracy, completeness, and consistency of the dataset. 

Examined the data to confirm that each value was assigned to the correct data type (e.g., numeric, text etc) and fell within the expected range of values. Any anomalies or inconsistencies in data typing and ranges were corrected.
Additionally, attention was given to the correct formatting and consistency of the entered data. The data was meticulously reviewed to ensure that it followed consistent formatting guidelines, such as date formats, decimal places, and alphanumeric representations. Inconsistencies in formatting were identified and rectified to maintain uniformity throughout the dataset.

The utilization of filters within the data table played a crucial role in the validation process. By applying filters, the data was examined to identify any irregularities, outliers, or discrepancies that may require attention. This allowed for a comprehensive assessment of the dataset's consistency, enabling the identification and resolution of any issues that could impact the accuracy or interpretation of the data.

Finally, a vital aspect of the data validation process involved checking for the presence of any blank spaces or missing values in the viewed data. The dataset was thoroughly examined to ensure that no essential information was missing or obscured by blank entries. Any instances of missing data were noted and addressed to maintain the completeness and reliability of the dataset.

By executing these comprehensive data validation measures, the project ensured that the dataset was free from abnormalities, maintained consistent formatting, and contained no missing values. This robust validation process bolstered the reliability and accuracy of the data, laying the foundation for accurate analysis and informed decision-making.

## Visualization

The data visualization stage of the Excel project involved transforming the analyzed information into meaningful and easily understandable visual representations. This allowed for a comprehensive overview of the modeled data on a dedicated dashboard, enhancing the viewer's ability to gain insights efficiently. Several key steps were taken to achieve this goal.

To begin, a new Excel sheet was created specifically for the purpose of visualizing the data. This dedicated sheet served as the canvas for assembling various charts, tables, and visual elements, consolidating all the modeled information in a single, easily accessible location. This approach ensured that viewers could review the data at a glance, enabling a holistic understanding of the analysis outcomes.

To enhance interactivity and provide viewers with more control over the data exploration process, slicers were incorporated into the dashboard. Slicers function as interactive filters that allow for further data segmentation based on different criteria and the specific interests of the viewer. By utilizing slicers, viewers can dynamically adjust the displayed data, focusing on specific subsets or dimensions of the analysis that are most relevant to their investigation.

These features collectively contribute to a more intuitive and user-friendly data visualization experience. By presenting the analyzed information on a dedicated dashboard, viewers can quickly grasp the key insights and trends without feeling overwhelmed by the complexity of the underlying data. The inclusion of slicers adds an extra layer of interactivity, enabling viewers to explore the data from different angles and refine their analysis based on specific filters of interest.

Through this data visualization process, the Excel project successfully addresses the initial research question regarding car insurance claim fraud. The consolidated dashboard and interactive slicers empower viewers to effortlessly navigate through the modeled data, facilitating a comprehensive understanding of the analysis outcomes while ensuring a streamlined and engaging data exploration experience.

## Analysis
Using the modelled data in the dashboard, I was able to answer the initial questions and provide insights on amazon online reviews.
At an initial look by using pivot tables and charts, most of the products received positive reviews. Around 6% of the products were rated excellent (4.5+), and 82% reviews were rated good (4.0-4.5), while 12% reviews were in the bracket (2.5-3.9). However when a descriptive analysis was done using the tool, we could see that the rating counts were skewed to the left while ratings were skewed to the right, which meant a few items received unusually large number of positive reviews ( >400,000). These few outliers have influenced the rating.
The electronics category received the maximum number of review counts and items like microSD cards under brand Sandisk stood as the top performer.
Amazon Basics was the top reviewed brand and their top reviewed products were Cables and Misc. items and  they have received unusually large number of reviews.
Amazon Basics was the top reviewed brand in all categories with the highest 4.5+ ratings, while boat received the maximum number of reviews in all.

A scatterplot chart plotted with discounted price vs rating counts hints that the selling price is influenced by the rating counts. 
Item with the highest selling price after discounts was a Sony Bravia 164 cm (65 inches) selling at Rs 77,990.00.
The histogram depicting the frequency of discount % shows us that it is slightly skewed to the right and max items reviewed were in a bracket of (55%-65%) discounts.


###Correlation: 
Through correlation analysis, it was determined that there is no statistically significant correlation between the variables.



## Conclusion
In conclusion, this project successfully analyzed amazon online reviews using Microsoft Excel, leveraging advanced techniques such as PivotTable, PivotChart, and Data Analysis. By investigating patterns associated with reviews and ratings, online platforms can enhance their product placing and strategies.

It was inferred that no significant correlation existed between the discounted price and ratings or review counts. 
Amazon seems to be a good platform to sell misc. electronic and computer accessories for a potential seller as can be seen from the plotted graphs. 
However one has to be cautious about unusually large volumes of ratings done for a not so significant product. They could be fake reviews but further analysis with more viable data is required to confirm. 






