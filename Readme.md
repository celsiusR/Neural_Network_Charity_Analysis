# Neural Network Charity Analysis

## Overview 

This project uses features in the charity_data.csv data set to create a binary classifier capable of predicting whether applicant will be successful if funded by Alphabet Soup. There are close to  34,200 organizations that previously received funding from Alphabet Soup. 

## Results

### Data Processing (Pre)

- `EIN` and `NAME are very specific and have no value as features and hence have been removed from the inputs.
- The column `IS_SUCCESSFUL` is binary. It is an indicator as to whether the charity donation was used. This component will be used as the target for deep learning neural network.
- `APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT` are all the features we will incorporate in our model. 
- I have encoded the categorical variables, and split them into the training and testing datasets and then standardized the features.

### Compiling, Training and Evaluating the model

- This deep-learning neural network model consists of two layers, one with 80 and the other with 30 neurons.
  The output layer being a binary classification consists of a unique neuron 
  The first and the second layer have the the RELU activation function. Given that the output is a binary classification, `Sigmoid` is used on the output layer.
  For the compilation, the optimizer used is `adam` and the loss function used is `binary_crossentropy`.
- With the model accuracy being below 75%, it is not optimum to predict the outcome of the charity donations.
- To increase the performance of the model,bucketing was applied to the feature `ASK_AMT` and was organized the different values by intervals.
  The number of neurons was increased on one of the hidden layers. A model with three hidden layers was used.
  The function (`tanh`) was employed but none of these steps helped improve the model's performance.

## Summary 

In summary, we present a deep neural network classification model that predicts loan applicant success from feature data contained in [`charity_data.csv`](https://github.com/jsheppard95/Neural_Network_Charity_Analysis/blob/main/Resources/charity_data.csv) with 73% accuracy. This does not meet the 75% accuracy target, and the optimization methods employed here have not caused significant improvement.

### Additional Optimization Methods

Performance could increase through additional optimization techniques such as visualizing the numerical feature variable `ASK_AMT` to find and remove potential outliers that could be causing noise. Additionally, one could iteratively tune the parameters above and keep optimal values when moving to subsequent parameters instead of reverting to the base setting and combining after completion. This would however require more careful thought on the order with which one adjusts parameters to arrive at an optimized model.

### Alternative Models

An alternative to the deep learning classification model presented in this project could be a more traditional Random Forest Classifier. This model is also appropriate for this binary classification problem and can often perform comparably to deep learning models with just two hidden layers. It is also advantageous in that there are less parameters to optimize and those which do require attention are more intuitive than those in a neural network.