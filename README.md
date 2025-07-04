# **AMAZON PRODUCT REVIEW ANALYSIS**

## PROJECT OVERVIEW
This project provides a comprehensive analysis of e-commerce transaction data for the Amazon product platform. This is built using Microsoft Excel, the project includes data cleaning, transformation, and visualization to uncover key insights about customer behavior, revenue trends, and product performance.
## TOOLS AND SKILLS USED 
1. Excel: For initial data exploration, cleaning, transformation and visualization.
2. Data Analysis Techniques: Including grouping, aggregation, and filtering.

## DATASET DESCRIPTION 
### The dataset contains information scraped from Amazon product pages, including:
- Product details: name, category, price, discount, and ratings 
- Customer engagement: user reviews, titles, and content
- Each row represents a unique product, with aggregated reviewer data stored as comma-separated values Total Records: 1,465 rows TotalFields: 16columns

 ## ANALYSIS TASKS
### Use pivot tables and calculated columns where necessary to answer the following: 
1. What is the average discount percentage by product category? 
2. How many products are listed under each category? 
3. What is the total number of reviews per category?  
4. Which products have the highest average ratings? 
5. What is the average actual price vs the discounted price by category? 
6. Which products have the highest number of reviews? 
7. How many products have a discount of 50% or more? 
8. What is the distribution of product ratings (e.g., how many products are rated 3.0, 
4.0, etc.)? 
9. What is the total potential revenue (actual_price × rating_count) by category? 
10. What is the number of unique products per price range bucket (e.g., <₹200, 
₹200–₹500, >₹500)? 
11. How does the rating relate to the level of discount? 
12. How many products have fewer than 1,000 reviews? 
13. Which categories have products with the highest discounts? 
14. Identify the top 5 products in terms of rating and number of reviews combined.

## DATA ANALYSIS PROCESSESS
1. DATA CLEANING: Unnecessary columns and blanks were deleted to allow a smooth analysis.

2. CALCULATED COLUMNS: Some columns required for analysis were not give from the primary data, hence the need for calculated columns. The processes and formulas for these columns are shown shown below;
### According to questions given, the required columns for the analysis are:
 - name
 - category
 - price
 - discount
 - ratings
 - rating count
 - user review
### Required calculated columns were then derived:
 - **product_category** from category (D2)
 ```
=LEFT(D2,FIND("|",D2) - 1)
```
 - **count_review_id** from review_id column (J2)
```
=LEN(J2)-LEN(SUBSTITUTE(J2,",",""))+1
```
 - **revenue** from actual_price (F2) and rating_count (I2)
```
=F2 * I2
 ```
 - **price_range_bracket** from actual_price (F2)
  ```
  =IFS(F2<200, "Less than 200",  AND(F2>=200, F2<=500), "Between 200 and 500", F2>500, "Greater than 500")
  ```
 - **discount_percentage_grouping** from discount percentage (G5)
  ```
  =IFS(G2=0%, "No Discount", AND(G2>= 1%, G2 <=20%), "Low Discount", AND(G2>=21%, G2<=50%), "Medium Discount", G2>=51%, "High Discount")
  ```
 ## ANALYSIS AND CALCULATIONS:
 ## Question 1; What is the average discount percentage by product category?
 ### From the data given, the category doesn't just contain the product categories, it contain more details of each product. According to product_category (a calculated column), there are just seven product categories; 
 - Car&Motorbike
 - Computer&Accessories
 - Electronics
 - Health&Personal Care
 - Home&Kitchen
 - OfficeProducts
 - Toys&Games
 ### A pivot table is then used. The 'product_category' in rows and 'discount_price' in values, the values is sum at default hence change it to average. 
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20175645.png?raw=true)

## Question 2; How many products are listed under each category?
###  The 'product_category' in rows and 'product_name' in values
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20180535.png?raw=true)

## Question 3; What is the total number of reviews per category?
###  The 'product_category' in rows and 'reviews_id' in values
![](https://raw.githubusercontent.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/2ece6676740fae5798ef7091e022c68af71ec7c4/Screenshot%202025-06-28%20180812.png)

## Question 4; Which products have the highest average ratings? 
###  The 'product_category' in rows and 'rating_count' in values
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20180851.png?raw=true)

## Question 5;  What is the average actual price vs the discounted price by category?
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20182227.png?raw=true)

## Question 6; Which products have the highest number of reviews?
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20182350.png?raw=true)

## Question 7; How many products have a discount of 50% or more?
```
=COUNT(IF(amazon!G2:G1388 >= 50%, 1, 0))
```
![](https://raw.githubusercontent.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/f12b20c75ad39ce4841821bc7e70e51918b79173/Screenshot%202025-06-28%20183242.png)

## Question  8;  What is the distribution of product ratings (e.g., how many products are rated 3.0, 4.0, etc.)? 
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20184442.png?raw=true)

## Question 9; What is the total potential revenue (actual_price × rating_count) by category? 
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20191518.png?raw=true)

## Question 10; What is the number of unique products per price range bucket (e.g., <₹200, ₹200–₹500, >₹500)? 
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20192327.png?raw=true)

## Question 11;  How does the rating relate to the level of discount? 
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20192659.png?raw=true)

## Question 12;  How many products have fewer than 1,000 reviews? 
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20193130.png?raw=true)

## Question 13; Which categories have products with the highest discounts? 
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20193405.png?raw=true)

## Question 14;  Identify the top 5 products in terms of rating and number of reviews combined. 
![](https://github.com/Vector-of-Gad/DSA-E-COMMERCE-ANALYSIS-PROJECT-/blob/main/Screenshot%202025-06-28%20193804.png?raw=true)

