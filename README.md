# Wholesale-customer-segmentation
- Segmenting the wholesale customer dataset.
-  The dataset refers to clients of a wholesale distributor. 
-  It includes the annual spending in monetary units (m.u.) on diverse product categories
-  EDA is performed with steps like Outlier removal, BoxCox transormation and normalization.
-  xgboostclassifier is performed on the clustered data to classify which channel they belong to .  

<b>VISUALIZATION</b>

<b> 1. Ranking with recursive Feature Elimination and Cross-Validated selection (RFECV)</b>
![RFECV](https://user-images.githubusercontent.com/94810983/147398801-03cbc69f-42ef-42de-8e40-e607ddffee06.PNG)

OBSERVATION:
  - RFECV is applied to find the optimal features.
  - We see that all 6 are important and should be considered.
  - More the number of features, higher the cv score is.
  - However, with 4 and 5 features, the cv score is same and is increased with the 6th .
  - Hence we will be considering all the 6 features in our modelling.


<b>2.ELBOW METHOD</b>
* ![kmeans](https://user-images.githubusercontent.com/94810983/147398817-0544bfaf-0d9a-485e-b78e-ef363a6b3ad9.PNG)
 
  OBSERVATION:
   - Elbow method is applied to find out the optimal clusters needed within the given range (2-15).
   - We see from cell 32 , three would be the approprite number of clusters.
   - K-means clustering is applied on the whole_processed_dfwith n_clusters=3.
   - With cluster_centers_ , the centroids values are got.
  
<b> 3. PCA and EXPLAINED VARIANCE</b>
  - ![variance](https://user-images.githubusercontent.com/94810983/147398861-0a375d38-6b28-4a9e-a005-0812c9dd5999.PNG)
  
  OBSERVATION:
- Plotting of explained variance by components is visualized.
-  we can infer from the above image that, the first two components are able to retain the original information accounting to 72% of the total and the first 4 components to 92.6% of the total.


<b>CONCLUSION</b>
- With regards to clustering, we can conclude that 3 clusters are ideal for this wholesale customer dataset. 
- Also, with RFECV we can conclude that all features are vital. With regard to Xgboost. 
- From the above implementation and evalutaion, we can say for this particular model of implementing Xgboost models, the maximum score achievable is 93%.
- We see that , with normal implementation without any tuning, is 90%. However, with Dtrain cv, we see that the maximum achievable accuracy_Score is is 93.9%.
