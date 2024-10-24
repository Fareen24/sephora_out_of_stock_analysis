

# Project Title: Sephora Product Stock Prediction

## Overview
This project aims to analyze and find out  which Sephora products are likely to go out of stock based on various factors such as price, customer reviews, and sales performance. By analyzing the dataset, we seek to uncover insights that can help Sephora improve its inventory management and sales strategies.

## Data Description


    The main features used for analysis are:

   price_usd: The price of the product.
   rating: Customer satisfaction rating.
   reviews: Number of reviews.
   loves_count: Indicator of product popularity.
   category (primary, secondary, tertiary): Product categorization.
   limited_edition: Whether the product is a limited edition.
   sale_price_usd: Discounted price.
   product_id: The unique identifier for the product from the site
   product_name: The full name of the product
   brand_id: The unique identifier for the product brand from the site
   brand_name: The full name of the product brand
   loves_count: The number of people who have marked this product as a favorite
   size: The size of the product, which may be in oz, ml, g, packs, or other units depending on the product type
   value_price_usd: 	The potential cost savings of the product, presented on the site next to the regular price
   limited_edition: 	Indicates whether the product is a limited edition or not (1-true, 0-false)
   out_of_stock: 	Indicates whether the product is currently out of stock or not (1 if true, 0 if false)
   sephora_exclusive: 	Indicates whether the product is exclusive to Sephora or not (1 if true, 0 if false)
  
   

   Feature engineered columns such as:
   price_bins: Grouped price categories.
   is_on_sale: Whether the product is currently on sale.
   stockout_rate: Stockout history for different categories.


## Deliverables
1. **Data Cleaning Notebook**:  
   ## Data Cleaning Process
- **Loading Data**: The data was loaded using pandas into a dataframe.
- **Handling Missing Values**: The method for dealing with missing values were dependent on the column. Use of mean, median, placeholders were used to fill the missing values.
- **Outlier Detection and Treatment**: To identify outliers in the dataframe I used boxplots to visualize the outliers. Then proceeded to handle the outliers using the capping method.

- **Feature Engineering**:New features were created such as, price bands, out of stock rate and out of stock rate based on category-level.
## Feature Engineering
  I created the price bins column that categorizes products into price ranges (price_bins) based on their price in USD (price_usd). Used the pd.cut() function  to bin the continuous price_usd values into discrete categories or ranges.
  In this case I divided the price groups as follows:
   From 0 to 20 USD is labeled as "Low."
   From 20 to 50 USD is labeled as "Medium."
   From 50 to 100 USD is labeled as "High."
   Prices above 100 USD fall into the "Premium" category. 
  
  To aggregate stock status by categories I grouped the data by each category then aggregated the total and out of stock rate.

2. **Exploratory Data Analysis (EDA) Report**:  
## Exploratory Data Analysis
From the EDA we uncovered several insights

1. Stock Availability Trends:

A notable percentage of products across various categories frequently go out of stock, indicating high demand or stock management issues in certain areas.
Categories like skincare, makeup, and fragrance exhibit higher out-of-stock rates compared to other product categories, suggesting potential areas where supply and demand need balancing.

2. Impact of Price on Stock Availability:

Products in the "Low" price range (under $20) are more likely to go out of stock, possibly due to higher affordability and demand from a wider customer base.
Conversely, "Premium" products (priced above $100) have lower out-of-stock rates, implying either lower demand or better stock management for these high-end products.

3. Product Category Performance:

Categories like "Limited Edition" products often have higher out-of-stock rates, which could be attributed to their exclusive and time-limited nature, driving demand.
Regular (non-limited edition) products tend to stay in stock longer, as they are likely produced in higher quantities or restocked more frequently.

4. Customer Behavior by Price Group:

Products that are "On Sale" often experience higher out-of-stock rates, particularly in the "Low" and "Medium" price ranges, indicating that discounts have a significant impact on stock depletion.
The introduction of sales or discounts, especially in affordable price categories, tends to accelerate stock turnover.

5.Product Reviews and Stock Correlation:

Products with higher customer reviews and better ratings are more likely to remain in stock longer. This may suggest that well-rated products are restocked faster or produced in higher volumes to meet consumer demand.
However, some highly reviewed products that go out of stock might highlight missed opportunities for maximizing sales due to inventory shortages.

6.Out-of-Stock Rate by Price Bin:

The analysis shows that the "Low" price bin has the highest out-of-stock rate, confirming that lower-priced products tend to sell faster.
The "Medium" and "High" price bins exhibit a more balanced stock availability, indicating that these products might be produced in sufficient quantities to match demand.









