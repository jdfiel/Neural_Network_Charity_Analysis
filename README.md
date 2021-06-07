# Neural_Network_Charity_Analysis

## Purpose
The purpose of the analysis is to develop a neural network model that will determine whether a company will be successful if Alphabet Soup decides to fund them.

## Data Preprocessing

* Our target variable is the “IS_SUCCESSFUL”, which makes sense as we are looking to determine  if a company will be successful once they receive funding from Alphabet Soup.

* The following are the features (and their unique values) of our model:
APPLICATION_TYPE            17
AFFILIATION                  6
CLASSIFICATION              71
USE_CASE                     5
ORGANIZATION                 4
STATUS                       2
INCOME_AMT                   9
SPECIAL_CONSIDERATIONS       2
ASK_AMT                   8747

* EIN and Name were not relevant to our model and were dropped.


Compiling, Training, and Evaluating the Model
How many neurons, layers, and activation functions did you select for your neural network model, and why?

Model Process:
* Neurons: The number of neutrons chosen were 80 and 30 initially, arbitrarily chosen. Increasing or decreasing the number of neurons per layer had little affect on accuracy/loss.
* Layers: The number of layers chosen were 2. Increasing or decreasing the number of layers had little affect on accuracy/loss.
* Activation Functions: The activation functions chosen were relu and sigmoid, as relu is a popular function and sigmoid is less impacted by outliers due to squashing.


Unfortunately, I was not able to achieve the desired performance.

Original Model:
![initial](https://github.com/jdfiel/Neural_Network_Charity_Analysis/blob/main/RM_Resources/initial_eval.png)

The following steps were taken to optimize the model:

Optimization 1:
* Added a third layer. 
![op1](https://github.com/jdfiel/Neural_Network_Charity_Analysis/blob/main/RM_Resources/Op1_eval.png)

Optimization 2:
* Changed Activation Functions (Note: various combinations were attempted but not all attempts were included. Final attempt was simply inverting between relu and sigmoid for the hidden and output layers)
![op2](https://github.com/jdfiel/Neural_Network_Charity_Analysis/blob/main/RM_Resources/Op2_eval.png)

Optimization 3:
* Increased epochs and additional hidden layer
![op3](https://github.com/jdfiel/Neural_Network_Charity_Analysis/blob/main/RM_Resources/Op3_eval.png)

Optimization 4:
* Increased epochs, neutrons and layers
![op4](https://github.com/jdfiel/Neural_Network_Charity_Analysis/blob/main/RM_Resources/op4_eval.png)

## Summary: 

Unfortunately, the model was unable to obtain a high level of accuracy. Looking at the initial model, the accuracy varied somewhat every time the model was rerun.

If we take a look at the original models epochs and compare it to the epochs of Optimization Run 4, we see that there isn’t a notable difference. In fact the optimization attempt had a lower accuracy score (though the accuracy score changed depending within the same model).

![initial_epochs](https://github.com/jdfiel/Neural_Network_Charity_Analysis/blob/main/RM_Resources/initial_epochs.png)

![op4_epochs](https://github.com/jdfiel/Neural_Network_Charity_Analysis/blob/main/RM_Resources/op4_epochs.png)

Looking at the epochs, we see that the initial model experiences higher loss and lower accuracy initially when compared to Optimization Run 4, but the final result are far less distant despite the additional layer and epochs.

This highly suggests that there is an issue with the data itself. It would be strongly recommended to review the data for any outliers. Specifically, looking at the unique values of our features, it is likely that ASK_AMT is skewing the data in some way.