# Retail-Recommender
  1. Introduction
  2. Objective 
  3. Data Dictionary
  4. Data Pre-processing
  5. Feature Engineering 
  6. Model Development 
  8. Results
# Introduction 
  1. There are many uses for a recommendation engine on e-commerece platoform <br>
  2. On top of strengthening relationsips with your customers, the right engine can provide higher returns to your business because it can help boost engagement opportunities with your product and offer a greater influx of cross-sell opportunities  <br>
  3. There are many advantages over developing recommender systems:<br>
       &nbsp;&nbsp;&nbsp;&nbsp; i.Drive Traffic<br>
       &nbsp;&nbsp;&nbsp;&nbsp; ii.Deliver Relevant content <br>
        &nbsp;&nbsp;&nbsp;&nbsp;iii.Engage shoppers<br>
       &nbsp;&nbsp;&nbsp;&nbsp; iv.Convert shoppers to customers<br>
       &nbsp;&nbsp;&nbsp;&nbsp; v.Increase average order value<br>
       &nbsp;&nbsp;&nbsp;&nbsp; vi.Increase number of items per order and a lot<br>
# Objective 
  1.The business wanted to understand if the customer is going to reorder a product based on his purchasing characterstics <br> 
  2.Apart from that, It is also important for business to understand the most frequently brought together(Market basket analysis) <br>
# Data Sources
  1. aisles.csv - This file consists of aisle id along with their description <br>
  2. departments.csv -This file consists of department id along with their description 
  3. prior.csv - This file consits of the past data 
  4. train.csv - This file consists of the training data 
  5. orders.csv - This file consits of information regarding orders which includes user id, days since prior order
  6. products.csv - This file consists of product id along with their description
# Methodology
## Feature Engineering
  1. Since the training data has only few features, a lot of other features can be added by using the information from other files
  2. From aisle file - Aisle information can be added to the data by merging that with the train file 
  3. From department file - Department information can be added to the data by merging that with the base file 
  4. From products file - Product description can be added to the base file 
  5. From orders file - Order information can be added to the base file 

With this, There are 134 features for 206K rows, which is huge dataset . So, Using Principal component analysis, The number of features can be reduced 
## Data Preprocessing 
### Principal Component analysis
  1.The whole features of 134 are being mapped to 30 components by covering the 99% variance from the data 
  2. The proportion variance explained is given by the below plot <br>
 <img width="298" alt="image" src="https://user-images.githubusercontent.com/89437135/155905665-4f0cfc5c-c953-4688-b9d3-85e0ac87998d.png"><br>
<br>
  4. The scree plot of the PCA components is given below<br>
  <img width="284" alt="image" src="https://user-images.githubusercontent.com/89437135/155905696-57576cd8-da6c-4c50-abf9-56ec6f471f7e.png"> <br>
  6. Using pairplot, It is very interesting to see the variance across different components<br>
  <img width="380" alt="image" src="https://user-images.githubusercontent.com/89437135/155905731-f527b77c-79b0-433e-b4fd-1aad7c68526e.png"> <br>
### K-Means Clustering 
  1. Our objective is to club the similar types of users in the data and understand the characteristics of the customer
  2. K-Means is used to segment the cusomters in different clusters  
  3. On the basis of the below elbow curve, 8 clusters are chosen to be ideal<br>
  <img width="290" alt="image" src="https://user-images.githubusercontent.com/89437135/155905760-6c219eeb-fe03-482c-bcfa-a7799c62c352.png"> <br>
  5. This the variance distribution between the clusters and principal components <br>
<img width="371" alt="image" src="https://user-images.githubusercontent.com/89437135/155905777-28c62740-eb45-4a03-9796-5ed96f786086.png"> <br>
# Model Development
   Model development is an iterative process. The predictor variable is continuous and the following approaches are being tested for prediction modelling<br> 
  1. Logistic Regression 
  2. Decision Tree
  3. Random Forest Classifier 
  4. Light GBM 
  5. CAT Boost 
  6. Xgboost Classifier <br>

For new customer, we can recommend products using association rule mining technique<br>

# Results 
  1. The Random forest classifier is turned out to be the best predictor for the given model with the test ROC of 88%
  2. For new customer, we can recommend products using association rule mininng technique
# Future Steps 
  1. With the additional data, The accuracy can be improved further to improve better customer experience
  2. Using NLP techniques, product description can also be used as feature to further improve the accuracy 
# Thank You! Our team won 3rd prize solving a business case in Tredence ML Hackathon 
