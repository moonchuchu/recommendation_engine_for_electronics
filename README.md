# Building recommendation system using Amazon Electronics Review dataset 


<br><br>

 ![image](https://user-images.githubusercontent.com/12857624/125155009-e9509c80-e111-11eb-8374-9b52d6da7cda.png)

<br><br>
### A good recommendation system boosts online sales revenue and many customers are dependant on onlilne market place's recommended product before making the final purchase.
<br>
Here, I will go over recommendation system building process using Amazon's Electronics review data. 
<br>
### 1. Data Review and Prep
a) The data is retrieved from Kaggle dataset : https://www.kaggle.com/prokaggler/amazon-electronic-product-recommendation. 
Originally the dataset has 78 million record. To reduce dataset volume, I used the sampling method first. It gave nice balance of 1-5 rating distribution but when it comes to product : rating volume ratio, the sampling resulted in data sparsity that product : rating ratio was only 1:3 while the original set has 1:9 ratio. 


![image](https://user-images.githubusercontent.com/12857624/125155197-10f43480-e113-11eb-8982-257a3d79f749.png)


b) By looking at user:product rating volume and by setting heuristic cut off which is users with at least 100 reviews, I was able to reduce the dataset to 44K from 78MM.

### 2. Model Building 
<br>
For the model building I used surprise package (https://surprise.readthedocs.io/en/stable/index.html) which is an easy-to-use Python scikit for recommender systems.
With surprise 1) k-NN Based Algorithm 2)Matrix Factorization Based Algorithms 3)Other Collaborative Filtering Algorithms were evaluated.


Here, 11 models were compared like below and for this selected Amazon eletronics dataset with 100 review users, the BaselineOnly algorithm gave us the best rmse.

<br>
![image](https://user-images.githubusercontent.com/12857624/125155483-1d798c80-e115-11eb-88b3-5b56d2df3e3d.png)

Since BaselineOnly algorithm gave us the best rmse, therefore, I trained and predicted with BaselineOnly and use Alternating Least Squares (ALS) which outputs 0.9484 as prediction rmse accuracy. 


### 3. Prediction 
 
In the final predictions notebook, we can take a look at rui and est for real user rating and predicted user rating.  

<br> Best Prediction

![image](https://user-images.githubusercontent.com/12857624/125156818-510be500-e11c-11eb-9c68-0e6ae68b4930.png)

<br> Worst Prediction

![image](https://user-images.githubusercontent.com/12857624/125156851-831d4700-e11c-11eb-8273-f72f32acc7d7.png)


