# neural-network-challenge-1: AI camp Module 18 challenge

## Overview

You work at a company that specializes in student loan refinancing. If the company can predict whether a borrower will repay their loan, it can provide a more accurate interest rate for the borrower. Your team has asked you to create a model to predict student loan repayment.

The business team has given you a CSV file that contains information about previous student loan recipients. With your knowledge of machine learning and neural networks, you decide to use the features in the provided dataset to create a model that will predict the likelihood that an applicant will repay their student loans. The CSV file contains information about these students, such as their credit ranking.

## Part 1: Prepare the data for use on a neural network model

In order to properly process and predict our data we are required to take pre-processing steps to get it in a consumable format. First we pull the data in from our source page and create our dataframe. We review the data to understand comlumns and rows represented and dtypes for each element. We then can and confirm our data is balanced with our target values 'credit_ranking'. Once we have reviewed our data we then make decisions to split out our features(x) and target(y) data elements. From this point we can utilize 'train_test_split' to create our testing and training data sets to be used by our model. Last step utilized in this workbook is to properly scale our data using 'standardscaler' for both test and train data so we are using normalized data elements for our model. 


## Part 2: Compile and Evaluate a Model Using a Neural Network

With our data now in a state we can utilize in a model we are tasked with creating a deep learning neural network to help predict credit quality for students. We start by defining our inputs(features) based on the length of our 'features' data. We then establish the number of layers required to process data accurately in this model. At this point we are prepared to create our 'keras' sequential model with the layers and nuerons set previously utilizing the 'relu' activation for inputs and 'sigmoid' activation function for our outputs. Now that our model has been created we can compile with (loss= 'binary_crossentropy', optimizer= 'adam', metrics= 'accuracy') parameters then fit our training data using 50 epochs to train. 
- Epoch 45/50
38/38 [==============================] - 0s 2ms/step - loss: 0.5097 - accuracy: 0.7598
Epoch 46/50
38/38 [==============================] - 0s 2ms/step - loss: 0.5078 - accuracy: 0.7590
Epoch 47/50
38/38 [==============================] - 0s 2ms/step - loss: 0.5065 - accuracy: 0.7598
Epoch 48/50
38/38 [==============================] - 0s 2ms/step - loss: 0.5053 - accuracy: 0.7615
Epoch 49/50
38/38 [==============================] - 0s 2ms/step - loss: 0.5046 - accuracy: 0.7623
Epoch 50/50
38/38 [==============================] - 0s 2ms/step - loss: 0.5029 - accuracy: 0.7623

Lastly we evaluate the model to determine loss and accuracy: 

- 13/13 - 0s - loss: 0.5098 - accuracy: 0.7350 - 180ms/epoch - 14ms/step
- Loss: 0.5097975730895996, Accuracy: 0.7350000143051147


## Part 3: Predict loan repayment success by using your neural network model

We now have a working model saved that we will recall to analyze how it performs with the test data that was split out early in the process and show the classification report. We first recall the model saved into a new variable to be used in next steps. Second step is to create data predictions from the test data and save as a dataframe rounded to then be anaylzed. Lastly we perform the classification report on the test data and predictions to identify accuracy: 

              precision    recall  f1-score   support

           0       0.69      0.78      0.73       188
           1       0.78      0.69      0.73       212

    accuracy                           0.73       400
   macro avg       0.74      0.74      0.73       400
weighted avg       0.74      0.73      0.73       400


## Part 4: Discuss creating a recommendation system for student loans

**1. Describe the data that you would need to collect to build a recommendation system to recommend student loan options for students. Explain why this data would be relevant and appropriate.**

The data I believe would be required to help support a recommendation system for student loans should be inclusive of the following list: 
- Previous loan payment history / credit rating - will help guide expected repayment or loan elgibility
- Student Education program(Major/course of study) - can help dictate potential earnings for ability to repay
- Student profile - Age / GPA / financial background / financial aid availability
- Student financial state - employment / current debt - ability to pay currently
- Loan details - amount required / terms - will establish amounts and schedule of payments
- Financial education - any course or learning on fiscal reponsibility
- Overall economic factors - current employment environment and loan policies

A combination of these data points would help create a reasonable scoring profile for student loan recommendations that could provide reliable predictability for loan repayment. 

**2. Based on the data you chose to use in this recommendation system, would your model be using collaborative filtering, content-based filtering, or context-based filtering? Justify why the data you selected would be suitable for your choice of filtering method.**

In order to create a robust recommendation system we should not rely on a single approach, instead a combination of at least two if not all three filtering approaches. By utilizing the 'content-based filtering' this would be able recommend based on loan characteristics and matching with the students ideal selections. We would also want to leverage the 'collaborative-filtering' to help provide recommendations based on students with a similar profile and successes with previous loans. 

**3. Describe two real-world challenges that you would take into consideration while building a recommendation system for student loans. Explain why these challenges would be of concern for a student loan recommendation system.**

Dealing with real world examples and data for a recommendation system we would need to be mindful of potential challenges that could be faced in this process. 
- Our system would have to be considerate of the financial and background information for college students. Frequently students don't have any past credit or financial histories so we will need to design mitigating steps where alternate methods will need to be used in scoring. Student earning potential will vary widely even within the same course of study so the system will need to be mindful of helping provide feasible repayment options that are affordable. 
- Our system would absolutely have to be focused on data privacy and regulation adherence in addition to consistent application of fair/non-biased recommendations for all students. Data privacy and regulations are paramount when creating a system that uses real people data for process. We would have to ensure we are meeting all regulatory needs and not producing illegal loans or exploiting students. Our system must be under constant supervision and perpetual evaluation for fair lending and non-bias recommendations. 

