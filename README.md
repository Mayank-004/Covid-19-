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
![image](https://user-images.githubusercontent.com/79218659/168509715-1fe87a31-7a7b-4b97-9cf7-1a174c6f494e.png)
![image](https://user-images.githubusercontent.com/79218659/168509759-79649d64-37e9-41a2-8715-457e5367eb11.png)


# FEATURE ENGINEERING

The task here is to prepare all dataset needed from raw data dataset before various modeling techniques processing to predict Covid 19 death cases. 

A.	Feature selection   

We derived our target column death from the column date_died. If provide two class label in our target column death as 0 and 1.
1 is being given to the person who is alive and in death cases 0 was allotted.
![image](https://user-images.githubusercontent.com/79218659/168509797-c537edfb-b8bf-4b1a-81ae-cf11dce9a03b.png)
![image](https://user-images.githubusercontent.com/79218659/168509841-7e1d2a9a-7db2-4c58-9990-8e54b3d8d826.png)
![image](https://user-images.githubusercontent.com/79218659/168509857-b8bf62ea-9e2f-4740-a462-55647689cf34.png)
![image](https://user-images.githubusercontent.com/79218659/168510008-0d228c0b-2695-4195-b052-c040a06a8fbc.png)



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
 ![image](https://user-images.githubusercontent.com/79218659/168510124-ab701c59-8323-4976-898d-d7be70208880.png)
 ![image](https://user-images.githubusercontent.com/79218659/168510222-6eed1b20-c0fd-4b32-91fc-af9b992ce480.png)
![image](https://user-images.githubusercontent.com/79218659/168510234-f44c2190-c399-4883-bafc-ec25212994de.png)
![image](https://user-images.githubusercontent.com/79218659/168510245-45b5d584-49b4-4205-82e8-17100521419d.png)
![image](https://user-images.githubusercontent.com/79218659/168510254-f066c69b-ee63-4ec5-bac8-4d74ce3d289d.png)
![image](https://user-images.githubusercontent.com/79218659/168510288-c0a66e9f-2643-45c6-90f9-da3889e78d55.png)


 
 # VGG16:
 On the basis of transfer learning, We have build an image recognition model to classify covid patients from non covid patients. This was being done through keras library and VGG16 architecture using imagenet dataset. Data used for training and testing purpose was downloaded from Kaggle.com which is a publicly available dataset
![image](https://user-images.githubusercontent.com/79218659/168510156-d8cdb866-81bd-420d-8555-a7e90f2edf4b.png)
![image](https://user-images.githubusercontent.com/79218659/168510369-3a86c590-6800-4bc8-a1d4-4a3e846603c3.png)
![image](https://user-images.githubusercontent.com/79218659/168510380-6d1ae5d2-f46a-4b64-a130-9f30caeb2fa2.png)
![image](https://user-images.githubusercontent.com/79218659/168510395-bc18d6c2-408b-4793-9f47-edef7601393f.png)
![image](https://user-images.githubusercontent.com/79218659/168510405-7ca20bf6-262b-4a23-83b6-44f0a2d23ee8.png)



# CONCLUSION AND FUTURE SCOPE

We can use these models to better understand the initial problem of the dataset and how to best determine whether a patient is at high risk of death and need more resources than normal patients.
From the comparison we could see, the Random Forest model with random oversampling gets a high accuracy, lesser time to be trained and high precision as well. It is important to consider the tradeoff between accuracy and the running time, in this project we would recommend predicting the customer airline satisfaction using the Random Forest method under random oversampling. 
![image](https://user-images.githubusercontent.com/79218659/168510414-544c9594-9893-49ee-b2b5-3d3808196bfc.png)


#Covid 19 Tableau Dashboard

# Covid19-Tableau-Dashboard ( OMICRON VARIANT )
<img width="1319" alt="image" src="https://user-images.githubusercontent.com/79218659/168657261-026b4066-5317-49b4-ad58-0b2fd55ab199.png">
<img width="1315" alt="image" src="https://user-images.githubusercontent.com/79218659/168657317-2cdf2543-1286-4f2a-b364-6f087e5541a5.png">
<img width="1017" alt="image" src="https://user-images.githubusercontent.com/79218659/168657351-384fa8b9-4432-495b-822d-d9e91c18e149.png">
<img width="1149" alt="image" src="https://user-images.githubusercontent.com/79218659/168657390-a71d99c6-6427-4e89-bfc2-b1c6e91483fd.png">
<img width="1243" alt="image" src="https://user-images.githubusercontent.com/79218659/168657427-695b6a5e-786c-4f69-8fb1-eacf0916dfcd.png">
<img width="1069" alt="image" src="https://user-images.githubusercontent.com/79218659/168657460-919c9b57-18f4-45b1-a4ef-f7aa4cc77ad9.png">
