# Amazon_Vine_Analysis

##Overview Analysis
- The dataset was selected and PySpark was used to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. PySpark was used to determine if there is any bias toward favorable reviews from Vine members in your dataset. Then, you’ll write a summary of the analysis for Jennifer to submit to the SellBy stakeholders.

## Dataset Utilized
- https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Health_Personal_Care_v1_00.tsv.gz

## Deliverables:
1. Perform ETL on Amazon Product Reviews
2. Determine Bias of Vine Reviews
3. Written Report on the Analysis

# Deliverable 1: Perform ETL on Amazon Product Reviews
- Amazon Review dataset is extracted as a DataFrame

![image](https://user-images.githubusercontent.com/90146132/153771597-eba6dea6-e911-4e86-8435-4787ca1a9246.png)

- The extracted dataset is transformed into four DataFrames with correct columns

![image](https://user-images.githubusercontent.com/90146132/153771634-71311ff2-a267-4064-b87e-df20e9e81105.png)

![image](https://user-images.githubusercontent.com/90146132/153771644-c71d6fbd-defb-4af7-8d57-55d1021bc06d.png)

![image](https://user-images.githubusercontent.com/90146132/153771655-22ee43a2-f626-4cf3-ac70-fca5bc4a3cf2.png)

![image](https://user-images.githubusercontent.com/90146132/153771672-bb6059db-e40c-4d32-9ec2-4976bb49e93e.png)

- All four DataFrames are loaded into their respective tables in pgAdmin

![customers_table](https://user-images.githubusercontent.com/90146132/153771723-257585ad-2766-4594-9384-183a50bf9789.png)

![products_table](https://user-images.githubusercontent.com/90146132/153771727-54bd80cb-ff5c-49db-b3bb-2b7e87a8d804.png)

![review_id_table](https://user-images.githubusercontent.com/90146132/153771734-8163b385-fdf2-40c3-bbf6-18ab81237b79.png)

![vine_table](https://user-images.githubusercontent.com/90146132/153771740-c553fdf1-bb08-4b1c-8059-3224d657b756.png)

# Deliverable 2: Determine Bias of Vine Reviews

![image](https://user-images.githubusercontent.com/90146132/153772420-9646a419-3510-4862-b93d-54a3c7e786bd.png)

![image](https://user-images.githubusercontent.com/90146132/153772436-fbbfc1c1-760c-4162-b52e-372ac9f9dc2a.png)

![image](https://user-images.githubusercontent.com/90146132/153772453-cd8634e9-d976-4a7e-93eb-fdc2c7bd4c78.png)

# Deliverable 3: Written Report on the Analysis
1. Using PySpark, we determined if having a paid Vine review makes a difference in the percentage of 5-star reviews.
2. Results:
  - How many Vine reviews and non-Vine reviews were there?
    Using our filtered dataframes for both vine and non-vine reviews, we were able to use the count function to find how many reviews there were for vine reviews (497) and non-vine reviews (120863).
    
![image](https://user-images.githubusercontent.com/90146132/153772667-1fdbc9ca-859b-4c89-bd5c-d25f4fd7bddf.png)

  - How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
    A dataframe was created for both vine and non-vine reviews. Using our filter function and filtering the star_rating column from each dataframe where it is equal to 5, we created two new dataframes for each instance. There were a total of 220 5 star ratings for paid vine reviews and 74470 5 star ratings for unpaid non-vine reviews.

![image](https://user-images.githubusercontent.com/90146132/153772924-da0d4f52-5247-4bb3-9e85-a24c53eff460.png)

  - What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
    Using the filtered dataframe with total count of 5 star reviews and the total count of reviews for both vine and non-vine reviews, we created two dataframes to find the percentage for both paid vine reviews and unpaid non-vine reviews. For paid vine reviews, the percentage was 44% and 62% percent for unpaid non-vine reviews.

![image](https://user-images.githubusercontent.com/90146132/153773152-03c20641-5291-4ba1-bbad-b7d32845122e.png)

3. Summary:
- Looking at our data analysis there were more unpaid non-vine reviews, 120863, compared to the paid vine reviews of 497. Out of those paid vine reviews, 220 were 5 star ratings which is 44% of the total number of vine review. Out of the unpaid non-vine reviews, 74470 were 5 star ratings which is about 62% of the total number of non-vine reviews. If we also look at the total count of helpfulvotes_df and filter to where the star_rating is equal to 5, we get a total of 74690. We can see that a majority of those 5 star ratings are from the non-vine reviews, which is 74470 reviews. This would conclude that the paid vine reviews provide minimal positive bias toward favorable reviews from Vine members in the dataset set since overall the majority of the 5 star rating reviews are unpaid non-vine.

![image](https://user-images.githubusercontent.com/90146132/153773932-4058482f-42c7-4a3d-bbbe-67c08e5d26c4.png)
    




