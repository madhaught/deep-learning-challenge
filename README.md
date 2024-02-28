# deep-learning-challenge
This repository is for the edX Data Analytics and Visualization Bootcamp affiliated with Case Western Reserve University. The assignment being completed in this repository is for module 21 - neural networks and deep learning. With provided starter code, I created the file AlphabetSoupCharity.ipynb (found in the Deep Learning Challenge folder). In that notebook I preproceesed data and created a neural network deep learning model. I saved the model in the file AlphabetSoupShcarity.ipynb. The second part of the assignment was to attempt to optimize the model. These optimization efforts are saved in the file AlphabetSoupCharity_Optimization.ipynb and the best model that I created in that notebook was saved as AlphabetSoupCharity_Optimization.h5. The final step of this assignment was to write a report on the performance of the deep learning model I created. That report is below in the README.md file.

I worked on this assignment with the help of tutor Reza Abasaltian.

# MODEL EVALUATION REPORT

## Overview:
The purpose of the analysis is to evaluate the deep learning model that I created. The model was created with data about funding Alphabet Soup's business ventures. Using features describing applicants for funding, the model is meant to predict if the venture will be successful if funded by Alphabet Soup.

## Results:

### Data Preprocessing:
* The variable that is the target for the model is if the venture will be successful, in the column "IS_SUCCESSFUL". 
* The variables that are features of the model are the type of application, the affiliation of the applicant, the classification of the application, the use case, the organizaton, the status of the organization, the amount of income of the applicant, if there were special considerations for the application, and the amount the applicant was requesting.
* Variables that I removed from the input data prior to analysis were the name of the applicant and their EIN. These variables were not relevant to analysis of the application.

### Compiling, Training, and Evaluating the Model:
* In the initial model I used an input layer, one hidden layer, and an output layer. The input layer had 80 neurons, the hidden layer had 30 neurons, and the output layer had 1 neuron. I used the relu activationfunction in the input and hidden layers and the sigmoid activation function in the output layer. I chose this based on the output provided in the starter code and on the models we created and analyzed during the bootcamp classes.
* The accuracy of the initial model was 72.97% The target performance of the model would be 75%
* The following were my attempts to improve model accuracy:
    * To attempt to improve the accuracy of the model, I first tried Hyperband tuning to find the optimal number of layers, neurons, and activation functions to employ. In doing this tuning I created a model that had 73.36% accuracy, closer to the target performance. 
    * I tried a second method of optimizatoin by using a random forest model to evaluate feature importance and eliminate features which appeared to have little importance to the model finding the target. Through this process I eliminated the STATUS and SPECIAL_CONSIDERATIONS features. I then created another instance of a deep learning model. This model had an accuracy score of 73.05%
    * The third method I tried to optimize the model involved using the features that I trimmed in the second attempt to create another tuner to find an optimal model with Hyperband tuning. The best model that resulted from this attempt had an accuracy of 73.35%. Because the
* I was not able to achieve the target performance but I got closest with my first attempt at optimization using the Hyperband tuning method.

## Summary and Recommendation:
The deep learning model that I created was close to the goal of performance goal of 75% accuracy, but fell short even with three attempts at optimization. Further attempts to optimize the model may get it closer to the goal performance score. I would recommend attempting the use of a decision tree or random forest model to solve this classification problem. Because the features used to predict the target are categorical a decision tree would be useful. If the model still had trouble predicting the data, it would be useful to employ a random forest model instead.