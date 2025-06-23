# **AMAZON PRODUCT REVIEW ANALYSIS**

## PROJECT OVERVIEW
### This project provides a comprehensive analysis of e-commerce transaction data for the Amazon product platform. This is built using Microsoft Excel, the project includes data cleaning, transformation, and visualization to uncover key insights about customer behavior, revenue trends, and product performance.

## DATASET DESCRIPTION 
### The dataset contains information scraped from Amazon product pages, including:
- Product details: name, category, price, discount, and ratings 
- Customer engagement: user reviews, titles, and content 

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
    
 ## ANSWERS
 ### According to questions given, the required columns for the analysis are just name, category, price, discount, ratings, rating count and user review. For optimal and easy analysis, clean the data i.e delete unnecessary columns.  
 ### Question 1; What is the average discount percentage by product category?
 ### From the data given, the category doesn't just contain the product categories, it contain more details of each product. Noticably, using a pivot table, there are just seven product categories; 
 - Car&Motorbike
 - Computer&Accessories
 - Electronics
 - Health&Personal Care
 - Home&Kitchen
 - OfficeProducts
 - Toys&Games
### Each of these categories has a delimeter of '|' which can be exploited to properly extract the product categories.
### The formula used is
    =LEFT(C2, FIND("|", C2) - 1 )
### A pivot table is then used. The 'product_category' in rows and 'discount_price' in values, the values is sum at default hence change it to average. 
![My Image](https://user-images.githubusercontent.com/your-image-url.png)

