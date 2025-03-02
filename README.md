# Comparing Classifiers

## Background
The data set represents 17 direct marketing campaigns conducted by a single Portugese bank that occurred between May 2008 and November 2010 including a total of 79354 contacts. Propsective customers were contacted via phone and presented an "attractive long-term deposit application, with good interest rates. An 8% success rate was observed over the entire dataset.

## Business Objective
Produce a machine learning model that helps improve the success rate of the client's marketing campaigns.

Our model should help the client reduce time spent on customers that are less likely to purchase. 

## Methodology
We first explored the dataset, prepped the data for training and then experimented with K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines to see which produced the best performing model for our purpose.

Assuming the cost of an additional phone call is outweighed by the revenue generated by success, we bias for a model that correctly predicts the largest number of succesful marketing attempts. To do this we scored model performance based on their recall.

## Results
### Recall
The Support Vector Machine produced the best Recall scores with a Training Data Recall of .993 and a Test Data Recall of .537.

A high training score with a much lower recall score suggests our model is good at identifiying positive cases in the training data, but not able to generalize this ability. 

Given the baseline recall score of 0, these results are still promising, but more feature engineering and hyperparameter tuning are needed to improve our results.

***Support Vector Machine : Recall***
*   Training Score : .993
*   Test Score : 0.537
*   C : 0.1
*   gamma : 10.0
*   kernel: 'poly'
*   Training Wall time: 2h 49min 44s

### A Brief Look at Accuracy
The Support Vector machine produced the best Accuracy scores with a Training Data Accuracy of ~.933 and a Test Accuracy of ~.912. 

***Support Vector Machine : Accuracy***
*   Training Accuracy : 0.933
*   Test Accuracy : 0.912
*   gamma: 0.1
*   kernel: rbf
*   Training Wall time: 30min 5s

It's likely an RBF kernel was selected by the GridSearchCV for its ability to represent non-linear relationships and model more complex decision boundaries - indicating our data my not be entirely linearly separable.

## Next Steps
*  Perform more extensive feature analysis to determine which are the most influential in our model's predicitve capabilities
*  Explore additional hyperparameters to better optimize for Recall performance
* With additional data from the client about the cost of each phone call and revenue earned from a success, we could further optimize our model to maximize revenue.
