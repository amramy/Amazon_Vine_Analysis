# Amazon Vine Analysis

## Overview:

The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are required to publish a review. 

Our purpose is to analyze the Amazon reviews and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Then use PySpark to determine if there is any bias toward favorable reviews from Vine members in your dataset.

### Results: 

After selecting the dataset "tools" and uploading them into a dataframe I was able to create the following four charts. 
 

#### Customers Table: 

<img width="372" alt="customers_table" src="https://user-images.githubusercontent.com/111904266/217395721-315cc70e-33af-4150-8a7c-4cd4b5a3ab1c.png">

#### Products Table: 

<img width="508" alt="products_table" src="https://user-images.githubusercontent.com/111904266/217395766-b36a2914-3a3c-40cd-92a7-3a10b17db814.png">

#### Review ID Table: 

<img width="521" alt="review_id_table" src="https://user-images.githubusercontent.com/111904266/217395835-e343ffda-3280-4a92-9e11-d6048a6e2e8d.png">

#### Vine Table: 

<img width="569" alt="vine_table" src="https://user-images.githubusercontent.com/111904266/217395881-ba06c934-0590-4ced-9c12-94a1fc8d1ae7.png">


### Determine Bias of Vine Reviews: 

* How many Vine reviews and non-Vine reviews were there?
  * 268 vine (worker) reviews & 29517 buyer reviews.

<img width="315" alt="total reviews" src="https://user-images.githubusercontent.com/111904266/217396217-a73b9600-0371-4206-aa9a-82f41690fa9b.png">


* How many Vine reviews were 5-stars? How many non-Vine reviews were 5 stars?
  * 149 vine (worker) & 13675 buyer reviews were 5 stars.

<img width="554" alt="5 star ratings" src="https://user-images.githubusercontent.com/111904266/217396241-da3b3d66-b502-47ba-aa12-18006e3b9499.png">

* What percentage of Vine reviews were 5-stars? What percentage of non-Vine reviews were 5-stars?
  *55.60% of worker reviews and 46.33% buyer reviews were 5-stars. 
  
<img width="470" alt="percent of 5-star reviews" src="https://user-images.githubusercontent.com/111904266/217396247-d8bb0104-e606-47e8-96d6-5da7f74be380.png">

### Additional Query:
* I was curious about how many non-vine members (the buyers) were verified purchases 
  * 16066 buyer reviews.
* How many buyers were unverified purchases? 
  * 13415 unverified buyer reviews.
* Of those unverified purchases how many had 5 star ratings.
  * 6003 unverified purchase 5-star reviews.

<img width="818" alt="verified and unverified reviews" src="https://user-images.githubusercontent.com/111904266/217396423-771dbd04-eaa5-4752-9578-e37462495980.png">


### Summary: 

* As the Amazon Vine members are a small percentage (0.9%) of the total 29,785 reviews and they did seem to have a bias towards a favorable review as there was almost 10% more 5 star reviews from Vine members than non-vine members. 
* In other words more than half (56%) of the 268 vine reviews were 5-star ratings
* My curiosity then led me to look at the buyer reviews and found that 45% of the 13,415 unverified buyers had 5 star reviews. 
* In other words 20% of the 29,517 buyer reviews were unverified 5-star reviews. 
