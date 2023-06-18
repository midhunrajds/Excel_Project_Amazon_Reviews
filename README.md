# Data Analysis Project using Excel – Amazon Reviews India
[![Microsoft Excel Badge](https://img.shields.io/badge/Microsoft%20Excel-217346?style=flat&logo=microsoftexcel)](https://www.microsoft.com/en-us/microsoft-365/excel)
[![PivotTable Badge](https://img.shields.io/badge/PivotTable-FFB200?style=flat&logo=microsoftexcel)](https://support.microsoft.com/en-us/office/create-a-pivottable-to-analyze-worksheet-data-a9a84538-bfe9-40a9-a8e9-f99134456576)
[![PivotChart Badge](https://img.shields.io/badge/PivotChart-FFB200?style=flat&logo=microsoftexcel)](https://support.microsoft.com/en-us/office/create-a-pivotchart-cb1f7c2c-5626-43b7-8e4a-87ecf35a9cac)
[![Data Analysis Badge](https://img.shields.io/badge/Data%20Analysis-FF7F50?style=flat)](https://en.wikipedia.org/wiki/Data_analysis)

![dashboard](https://github.com/midhunrajds/Excel_Project_Amazon_Reviews/assets/126799337/3f088b0f-695f-4c41-b383-3d37bea625cc)

<a name="top"></a>
# Index

- [Abstract](#abstract)
- [Introduction](#introduction)
- [Context/Problem](#Context/Problem)
- [Purpose of the Study](#Purpose%20of%20the%20Study)
- [Project Description](#Project%20Description)
- [Features](#features)
- [Data Cleaning Process](#Data%20Cleaning%20Process)
- [Exploratory Data Analysis](#Exploratory%20Data%20Analysis)
- [Conclusion](#Conclusion)
- [License](#license)

## Abstract
The primary intention is to gain insight into the product reviews on Amazon and look out for any interesting patterns that may help in better product placement and strategy for potential sellers.

## Introduction
The dataset used in this analysis contains the data of 1K+ Amazon products' ratings and reviews as per their details listed on the official website of Amazon. The dataset was obtained from [Kaggle.com](https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset). This dataset is licensed under a Creative Commons Attribution 4.0 International (CC BY-NC-SA 4.0) license, allowing for the sharing and adaptation of the datasets for any purpose, provided that the appropriate credit is given.

## Context/Problem
This dataset consists of more than 1000 real products with their identification numbers listed in the Amazon marketplace. The aim of the project is to gain insights into the review and rating patterns, identify top-performing segments and brands on Amazon India, and identify any interesting correlations between the features.

## Purpose of the Study
The project aims to apply various techniques and tools learned in data science to solve problems. The outcome of the project will provide insights into rating and review patterns. On an organizational level, it can help in better placement of strategies to increase sales and optimize the online experience for customers.

## Project Description
Various data analytics techniques are applied to explore the data. The CRISP-DM process is followed to ensure a proper methodology. The data preparation involves fixing issues such as missing values and disorganization using appropriate methods like imputation and removal. Most of the attributes are relevant to the analysis. The dataset has 1465 sessions and 16 columns in the original CSV format. The file was converted to XLS for ease of use and compatibility.

![raw](https://github.com/midhunrajds/Excel_Project_Amazon_Reviews/assets/126799337/d2b866cc-ce7d-4f69-bafd-c5cd86f6da84)

### Features
- product_id - Product ID
- product_name - Name of the Product
- category - Category of the Product
- discounted_price - Discounted Price of the Product
- actual_price - Actual Price of the Product
- discount_percentage - Percentage of Discount for the Product
- rating - Rating of the Product
- rating_count - Number of people who voted for the Amazon rating
- about_product - Description about the Product
- user_id - ID of the user who wrote a review for the Product
- user_name - Name of the user who wrote a review for the Product
- review_id - ID of the user review
- review_title - Short review
- review_content - Long review
- img_link - Image Link of the Product
- product_link - Official Website Link of the Product

## Data Cleaning Process:

Features `discounted_price`, `actual_price`, `discount_percentage`, `rating`, and `rating_count` were converted to numerical datatype for analysis purposes. Further cleaning was required as Excel was not identifying the currency symbol for the prices. Data cleaning steps done on the numerical data columns:
- `discounted_price` – datatype converted to number. This is a ratio level data.
- `actual_price` – same as above.
- `discount_percentage` – float value between 0 and 1.
- A new column (`discount_bracket`) was created by converting the values to segments based on discount brackets for easier analysis using nested IF statements.
- `Rating` – Rank order data/ordinal datatype similar to Likert scale. There was one null field. The same was replaced with the MODE of the column, which was 4.1.
- Ratings ranged from 2 to 5, with 2 being the lowest and 5 being the highest review rating received.
- A new column (`rating_bracket`) was created to convert the ratings into segments similar to poor, average, good, and excellent using nested IF statements.
- `rating_count` – number value, quantifiable.

The rest of the features were categorical datatype, and for the purpose of my analysis, I will be using the below features from the remaining:
- `product_id` – String text. Nominal Data.
- `product_name` – A long string with the brand name at the beginning. Used the `=LEFT` function to extract the brand name and placed it in a new column (`brand`). The brand column had some ambiguous data with typos and mismatches caused due to spacings. These were fixed using the `=PROPER` and `=TRIM` functions, as well as the Find & Replace function as required. For example, "Amazonbasics" and "Amazon Basics" were the same brand but identified as different due to typos.
- `category` – a long string with category and subcategory separated by "|". Used the text-to-columns function to split the string and create new columns for category and subcategories. As some of the newly created columns had many null values and were repetitive in nature, only the category and subcategory columns were retained. The missing values in the subcategory column were replaced with "Misc" for null values.
- The rest of the categorical features were not useful for the exploratory purpose using Excel, as they were lengthy strings with no strict datatype followed (user_id, review description, etc.), so they were discarded.

![working](https://github.com/midhunrajds/Excel_Project_Amazon_Reviews/assets/126799337/d23b4ca9-b3a5-4a59-afd6-2a30893a8b61)

## Exploratory Data Analysis:

### Manage missing data and outliers:
There was one null field in the `rating` column. The same was replaced with the MODE of the column, which was 4.1.
Unusually large review counts were found for some products, but they would probably be considered outliers as they were for products sold directly by Amazon Basics.
Data normalization can be done for these numbers using z-score or min-max normalization if required.


### Key insights visualizations:
The cleaned dataset was converted to a table, and pivot tables were inserted to explore relations and create graphs and 2-D stacked columns.

<img width="959" alt="pivot" src="https://github.com/midhunrajds/Excel_Project_Amazon_Reviews/assets/126799337/e1c5e6d5-4e1f-4c40-9977-9c3fe1b5df8e">


### Validation

During the data validation phase of the Excel project, checks were done to ensure the accuracy, completeness, and consistency of the dataset. 

Examined the data to confirm that each value was assigned to the correct data type (e.g., numeric, text etc) and fell within the expected range of values. Any anomalies or inconsistencies in data typing and ranges were corrected.
Additionally, attention was given to the correct formatting and consistency of the entered data. The data was meticulously reviewed to ensure that it followed consistent formatting guidelines, such as date formats, decimal places, and alphanumeric representations. Inconsistencies in formatting were identified and rectified to maintain uniformity throughout the dataset.

The utilization of filters within the data table played a crucial role in the validation process. By applying filters, the data was examined to identify any irregularities, outliers, or discrepancies that may require attention. This allowed for a comprehensive assessment of the dataset's consistency, enabling the identification and resolution of any issues that could impact the accuracy or interpretation of the data.

Finally, a vital aspect of the data validation process involved checking for the presence of any blank spaces or missing values in the viewed data. The dataset was thoroughly examined to ensure that no essential information was missing or obscured by blank entries. Any instances of missing data were noted and addressed to maintain the completeness and reliability of the dataset.

By executing these comprehensive data validation measures, the project ensured that the dataset was free from abnormalities, maintained consistent formatting, and contained no missing values. This robust validation process bolstered the reliability and accuracy of the data, laying the foundation for accurate analysis and informed decision-making.


## Visualization

The data visualization stage of the Excel project involved transforming the analyzed information into meaningful and easily understandable visual representations. This allowed for a comprehensive overview of the modeled data on a dedicated dashboard, enhancing the viewer's ability to gain insights efficiently. Several key steps were taken to achieve this goal.

Through this data visualization process, the Excel project successfully addresses the initial research question regarding car insurance claim fraud. The consolidated dashboard and interactive slicers empower viewers to effortlessly navigate through the modeled data, facilitating a comprehensive understanding of the analysis outcomes while ensuring a streamlined and engaging data exploration experience.

<img width="1434" alt="dashboard" src="https://github.com/midhunrajds/Excel_Project_Amazon_Reviews/assets/126799337/3f088b0f-695f-4c41-b383-3d37bea625cc">

[Go back to top](#top)

## Analysis

+ Using the modelled data in the dashboard, I was able to answer the initial questions and provide insights on amazon online reviews.
At an initial look by using pivot tables and charts, most of the products received positive reviews. Around 6% of the products were rated excellent (4.5+), and 82% reviews were rated good (4.0-4.5), while 12% reviews were in the bracket (2.5-3.9). 

+ The electronics category received the maximum number of review counts and items like microSD cards under brand Sandisk stood as the top performer.
+ Item with the highest selling price after discounts was a Sony Bravia 164 cm (65 inches) selling at Rs 77,990.00.
Amazon Basics was the top reviewed brand and their top reviewed products were Cables and Misc. items and  they have received unusually large number of reviews.
+ Amazon Basics was the top reviewed brand in all categories with the highest 4.5+ ratings, while boat received the maximum number of reviews in all.

+ However when a descriptive analysis was done using the tool, we could see that the rating counts were skewed to the left while ratings were skewed to the right, which meant a few items received unusually large number of positive reviews ( >400,000). These few outliers have influenced the rating.

<img width="1074" alt="descriptive" src="https://github.com/midhunrajds/Excel_Project_Amazon_Reviews/assets/126799337/d2539437-48b0-4451-b9d2-7c62c7aa0039">

+ A scatterplot chart plotted with discounted price vs rating counts hints that the selling price is influenced by the rating counts. 
<img width="1440" alt="ndata" src="https://github.com/midhunrajds/Excel_Project_Amazon_Reviews/assets/126799337/a92f90fa-ce7b-45a2-b43f-82ae47cf67b3">
+ The histogram depicting the frequency of discount % shows us that it is slightly skewed to the right and max items reviewed were in a bracket of (55%-65%) discounts.
<img width="1440" alt="scatterplot" src="https://github.com/midhunrajds/Excel_Project_Amazon_Reviews/assets/126799337/b76f0b1c-61f7-49c4-938d-a5b725bb10b1">

### Correlation: 
Through correlation analysis, it was determined that there is no statistically significant correlation between the variables.

## Conclusion
In conclusion, this project successfully analyzed amazon online reviews using Microsoft Excel, leveraging advanced techniques such as PivotTable, PivotChart, and Data Analysis. By investigating patterns associated with reviews and ratings, online platforms can enhance their product placing and strategies.

It was inferred that no significant correlation existed between the discounted price and ratings or review counts. 
Amazon seems to be a good platform to sell misc. electronic and computer accessories for a potential seller as can be seen from the plotted graphs. 
However one has to be cautious about unusually large volumes of ratings done for a not so significant product. They could be fake reviews but further analysis with more viable data is required to confirm. 

[Go back to top](#top)





