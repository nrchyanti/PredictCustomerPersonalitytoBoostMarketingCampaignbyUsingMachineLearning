# Predict Customer Personality to Boost Marketing Campaign by Using Machine Learning
A company can grow rapidly when it knows the behavior of its customer personality. Because by knowing customer behavior, companies can provide better services and benefits to customers who have the potential to become loyal customers. By processing historical marketing campaign data, companies can improve performance and target the right customers so they can transact on the company's platform. From this data insight, our focus is to create a cluster prediction model to make it easier for companies to make decisions.

## Conversion Rate Analysis Based on Income, Spending and Age
![image](https://user-images.githubusercontent.com/101455281/189037510-5fd4b605-7796-42dd-bdfa-50a2fa7eb732.png)

The correlation between numeric columns can be seen on the heatmap. We focus on seeing the correlation of conversion_rate with other columns.

![image](https://user-images.githubusercontent.com/101455281/189037601-92bf7899-4376-4b46-92cc-e036ae6e1410.png)

The correlation of conversion_rate with age is the weakest. This means that age and conversion_rate do not affect each other.

![image](https://user-images.githubusercontent.com/101455281/189037768-ec04b9dc-f9d8-4085-8198-018306ae6751.png)

Other features that correlate quite strongly with conversion_rate are Income, total_spent, and total_purcases. All of them are positively correlated, which means that the larger the value of these columns, the higher the conversion_rate. The distribution of Income, total_spent, and total_purcases data compared to conversion_rate can be seen in the scatter plot above.

![image](https://user-images.githubusercontent.com/101455281/189037826-68c18568-36dd-4c82-adff-954e63f4608a.png)

If we look at the type of customer whether they are parents or not, it turns out that customers who are married and have children have a lower average conversion_rate compared to customers who are not married or who are married but do not have children.
This is consistent with the data that customers who do not have children have the highest average conversion_rate compared to customers who have 1 or more children.

![image](https://user-images.githubusercontent.com/101455281/189051150-e522606d-d5dc-4206-bdc8-ec0925cef1d9.png)

The greater the income, there is a tendency to have more expenses and have a larger total expenditure on our platform.

### Recommendation
We can choose customers who have income of 60 million and above for marketing campaigns by targeting many people who have CVR above 10%. 

**But what about the other groups, can we do something about them?**

## Data Cleaning & Preprocessing
- There are 24 missing values in the Income column. Because the number is relatively small compared to the entire data, the data rows that have this missing value will be deleted.
- There are no duplicate rows in the data.
- Feature encoding performed on the GroupAge and is_parent columns using the label encoding. Especially for is_parent column, the 'No' and 'Single' are given the 0 value. While the 'Yes' data is 1.

### Data Snippets Ready to Modelling
![image](https://user-images.githubusercontent.com/101455281/189054802-3e7d6eaf-6ab9-4b84-9b63-45accbaa5025.png)

## Data Modelling

![image](https://user-images.githubusercontent.com/101455281/189059624-42eab1a2-10a8-4e7a-ab02-bfdf3268729f.png)

The results curve for the elbow method is shown in the image above. It can be seen that the slope begins to decrease from 4 to 5. So that 4 clusters will be selected to perform the k-means clustering model.

![image](https://user-images.githubusercontent.com/101455281/189089969-e1c36d9f-da4e-4f12-82b6-2e5afb102df3.png)

Using the k-means algorithm, the data is divided into 4 clusters. The distribution of the data can be seen in the scatter plot above. The data is divided into 4 clusters based on the feature Income, total_spent, and conversion_rate.

## Customer Personality Analysis for Marketing Retargeting

The results of customer clustering which are divided into 4 groups based on the average total spent, average income, and average conversion rate can be seen in the following diagram.

![image](https://user-images.githubusercontent.com/101455281/189099810-7277cc14-a36e-43d9-84c3-aad367208017.png)

### Low Potential Customer
Customers of this cluster have low income with very low total product purchases. The conversion rate is also very low, which means these customers are not interested in visiting the store and are not interested in buying. This treatment for customers can be done by providing regular advertisements to find out customer interest in the company's products.

![image](https://user-images.githubusercontent.com/101455281/189097117-50cd25bd-771b-41eb-8693-c766833a5f68.png)

### Potential Customer
This cluster customer has a fairly high income with a very high total product purchase. However, the conversion rate tends to be low, which means that these customers often make purchases without having to visit the store many times or make large purchases for each transaction. This treatment for customers can be done by providing special promos for purchases with a large minimum nominal.

![image](https://user-images.githubusercontent.com/101455281/189097460-5c10b035-6cc0-401b-91f9-3b6bf04a76ba.png)

### High Potential Customer
This cluster customer has the highest income followed by a very high total product purchase. The conversion rate is also very high, which means that this customer is a loyal customer and makes the most frequent transactions. This treatment for customers can be done by prioritizing customers and maintaining service quality so that customers are not disappointed. You can also be rewarded if you make a certain number of transactions.

![image](https://user-images.githubusercontent.com/101455281/189097616-e64f0eeb-36b4-48dd-bb22-995bb47f236e.png)

### Medium Low Potential Customer
Customers of this cluster have sufficient income with low total product purchases. The conversion rate is also low, which means these customers are not very interested in buying the product. This treatment for customers can be done by providing regular advertisements and providing attractive promos for items that are of interest to this cluster customer.

![image](https://user-images.githubusercontent.com/101455281/189097726-bc0e6ada-6ac1-4e6a-9dc4-291b59c3c3dd.png)
