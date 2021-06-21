# Introduction:

Our dataset was originally sourced from 
https://www.gob.mx/salud/documentos/datos-abiertos-152127   and released by Mexican 
government. It is open for any public usage/research while the source of the data is anonymous. 
This dataset is related to global pandemic Covid 19. One of the main problem that healthcare 
providers face is shortage of medical resources an efficient distribution of these resources to 
most needy ones. This dataset can help predicting what kind of resources are required to what 
type of patient on the basis of medical history and other historical facts It was last updated on 
July 22, 2020. The dataset contains anonymized patient related data to predict features correlated 
with covid 19, which is saved in “.CSV” file format. Altogether there are 23 columns and 
5,66,602 rows. Many of the columns are ordinal factors that assigns patients medical situation a 
label. 


# FEATURE ENGINEERING

The task here is to prepare all dataset needed from raw data dataset before various modeling techniques processing to predict Covid 19 death cases. 

A.	Feature selection   

We derived our target column death from the column date_died. If provide two class label in our target column death as 0 and 1.
1 is being given to the person who is alive and in death cases 0 was allotted.



# MODELING TECHNIQUES

After preparing the data, we can implement several tree-based methods and set performance metrics to evaluate their performance with our passenger data.

A.   Models 

1)	  Random Forest
A random forest model is an ensemble machine learning algorithm that creates multiple uncorrelated decision trees by taking a bagging approach to sampling along.
It differs from bagging as it takes a random selection of features as opposed to all of them.
The collective results from these trees are then used to make a classification for a given datapoint. 
Random forests is very accurate dealing with non-linear data as well as outliers and works well with large datasets. 
Conversely though, the training process is notably slow.  This approach can help us determine whether a given patient is at high risk of death or not.

A function is defined to easily call and evaluate our model performance by displaying accuracy information and plots. An example of this is shown below:
 
A user defined function has been made to calculate time taken to train the model. It may further help us analyzing performance and model selection.


The number of trees to use is defined in the variable n_estimators_hyp, and the minimum number of samples required to split an internal node is defined in the variable min_sample_leaf_hyp.
 
       The RandomForestClassifier function from the sklearn library is called within a nested for-loop to create the models with each of the parameters. For example, a random forest with 100 trees is created with a minimum of 10 leaves. A few iterations of the models are collected and shown below with their Out-of-Bag score.
 
 
       The OOB score represents the accuracy rate for based on the number of correctly predicted values from the out-of-bag sample. With this information, a random forest model is created using 400 trees and a minimum of sample leaf of 1 is stored. The OOB score for this model is approximately 0.9632.
 

 Calling our custom eval_result function allows us to see the overall accuracy of this random forest model. We got the best result with random forest with random oversampling.The  accuracy for the training dataset is approximately 93%  and for testing dataset is 91% and the area under the ROC curve for it is about 0.97. However, since it is a highly imbalanced dataset, we have also paid attention to Precision Recall curve and area under PR curve is 0.99 which is encouraging



# CONCLUSION AND FUTURE SCOPE

We can use these models to better understand the initial problem of the dataset and how to best determine whether a patient is at high risk of death and need more resources than normal patients.
From the comparison we could see, the Random Forest model with random oversampling gets a high accuracy, lesser time to be trained and high precision as well. It is important to consider the tradeoff between accuracy and the running time, in this project we would recommend predicting the customer airline satisfaction using the Random Forest method under random oversampling. 


