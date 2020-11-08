# Amazon Apparel Customer Rating Analysis :dress:
### ETL Analysis on Big Data using Python, SQL, and AWS

## Overview of Amazon Customer Rating Analysis

The purpose of this analysis is to work with and perform an ETL process on big data and store it with Amazon Web Services (AWS). The dataset used in this analysis is from a Amazon Customer Review database that contains two types of customer feedback: paid and unpaid reviews. This dataset includes information about various apparel styles from an Amazon program called Vine that was responsible for conducting the paid reviews. Amazon Vine is a service that allows manufacturers and publishers to receive reviews for their products. Companies pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. 

In the analysis, we clean up the data, transform and filter it with dataframes and then store it in pgAdmin SQL tables in a server connected to AWS. Once it is cleaned, analysis is conducted to determine whether there is any bias in the reviews of the Vine program, compared to unpaid customer reviews.

The tools used in this analysis are: Python with PySpark in Google Colab (used to transform and clean the dataset), pgAdmin with SQL tables, and AWS servers. 

## Storage in AWS 

Since the dataset in this analysis is so large, it is important to store it on a cloud based server. This data is uploaded to the AWS using pgAdmin. Below are screenshots of the dataset stored in various SQL tables in pgAdmin. 

<img width="253" alt="customers_table" src="https://user-images.githubusercontent.com/67871338/98471863-2ba98e80-21bd-11eb-9ecc-4c5c3a91bbaf.PNG">          <img width="255" alt="products_table" src="https://user-images.githubusercontent.com/67871338/98471865-2e0be880-21bd-11eb-802a-bbda2994272d.PNG">

<img width="458" alt="review_id_table" src="https://user-images.githubusercontent.com/67871338/98471866-2fd5ac00-21bd-11eb-9582-3732278c36d9.PNG"><img width="517" alt="vine_table" src="https://user-images.githubusercontent.com/67871338/98471870-32380600-21bd-11eb-8bad-4f7d71e03065.PNG">

## Results 

### 1. How many Vine reviews and non-Vine reviews were there? 
Once the dataset was cleaned (filtered for total votes over 20, and whether helpful votes/total votes is >= 50%), there were 45,421 total reviews. 
There were 33 total paid Vine reviews and 45,388 unpaid reviews. 

### 2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars? 
There are only 15 five star Vine reviews. There are 23,733 five star unpaid reviews. 

### 3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars? 
45% of Vine reviews were five stars. 52% of non-Vine reviews were five stars. 

## Summary 

In conclusion, there are a few different points to call out about the Vine paid reviews vs. unpaid reviews. 

- There are only 33 total reviews for the paid program, compared to 45,388 unpaid reviews. This means that there is a lot more valuable insight to gather from the unpaid reviews since the dataset is much larger. 
- There is negative bias for the paid reviews, as the % to total of 5 star reviews was only 45% compared to unpaid at 52%. This means that the customers rating the product might have been more critical because they were being paid for their insight. Those who left unpaid reviews were responding more accurately because there was no outside influence on their opinions or reviews. 
- In order to support this conclusion, I would also look at other ratings in the reviews. Perhaps the paid Vine reviewers rated more things with a 4 instead of 5 compared to unpaid reviews (and had a higher percentage of 4 star ratings). This could be because they didn't want to always provide 100% satisfaction with the product since they were being paid and wanted to appear that they were being critical of the product. 
