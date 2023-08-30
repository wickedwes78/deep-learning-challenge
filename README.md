# deep-learning-challenge

## Module 21 Challenge

**_Performance Report - Neural Network Model_**  
_Utilising prior funding metadata_

Overview of the analysis: Alphabet Soup have requested a tool to assist with selecting applicants for future funding with teh best chance of success in their ventures. As a result I have utilised the metadata provided to create a Nueral Network Model to assist with future funding applicant selections.

Results: Using bulleted lists and images to support your answers, address the following questions:

### Data Preprocessing

**[Deep_Learning_Train](Deep_Learning_Train.ipynb)**  
What variable(s) are the target(s) for your model? The 'IS_SUCCESSFUL' is the only target for my model.  
What variable(s) are the features for your model?  The variables utilised where - APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS and ASK_AMT. APPLICATION_TYPE AND CLASSIFICATION were bucketed to reduce the unique values below 10.  
What variable(s) should be removed from the input data because they are neither targets nor features? The variables EIN and NAME, both identification columns were removed from the input data.  

Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why? In this model, I utilised the following nuerons, layers, with an activation of relu and sigmoid. The number of neurons was based on the number of columns + one for a bias term for the second layer and then half of that for the final layer.  
![image](https://github.com/wickedwes78/deep-learning-challenge/assets/127099343/7c300606-e345-4b8f-9d0d-7433d5fd7f72)

Were you able to achieve the target model performance?  No, the accuracy utilising the above model was only 72.8%.  

**[Deep_Learning_Optimisation](Deep_Learning_Optimisation.ipynb)**  
What steps did you take in your attempts to increase model performance?  
I first created a sequential model with hyperparameter options to determine the best model based on the train model above.  Then I utilised that information after updating the variables as below:  
What variable(s) are the target(s) for your model? As above, the 'IS_SUCCESSFUL' is the only target for my model.  
What variable(s) are the features for your model?  The variables utilised where as above - NAME was reincluded and bucketed to reduce the unique values below 10.
What variable(s) should be removed from the input data because they are neither targets nor features? The variable EIN, identification column was removed from the input data.  I removed the entities with a status of of 0, being not active.  
In this model, I utilised the following nuerons, layers, with an activation of relu and sigmoid.  
![image](https://github.com/wickedwes78/deep-learning-challenge/assets/127099343/89ba35d3-a01a-433a-bc33-e3468d2999fb)

The accuracy utilising the above model increased to 74.6% still below the required 75%.  

### Summary  
While the accuracy of the optimisation model is below 75%, the accuracy increase appears to be from the inclusion of NAME back into the data. This may be a bias outcome as the name should not determine who you would provide funding to, but due to the nature of the bucketing, the majority of the NAME column was allocated to 'other', therefore not biasing the outcome.  
Further adjusting of the model may not lead to a higher accuracy and consideration needs to be given in relation to the business structure of the applicants that is not able to be included in the dataset.  A 74.6% accuracy model could be utilised by Alphabet Soup along with their current method of assessing applicants to determine if it assists with the selection process.  



**External resources used**

https://re-thought.com/pandas-value_counts/  
https://www.tensorflow.org/tutorials/keras/save_and_load
