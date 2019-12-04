# Ensemble-model

Bank Marketing use direct marketing campaigns in order to motivate and attract clients to offer loan. Credit scoring is a widely used technique that helps banks to decide whether to grant loan to a consumer or not. In building the credit scoring models from a banking data is a challenging a task and statistical classification models perform reliable well in meeting essential assumptions.

Ensemble learning model used to make prediction on client who most likely will contacted based on credit score. The dataset  used in training ensemble models – Bagging, Boosting and Random Forest in Caret package in R.  

In caret package , use C5.0 decision tree to train the model in R. This model Deposit using all of the other features in the Bank Marketing data frame. The parameter method = "C5.0" tells caret to use the C5.0 decision tree algorithm.

The data pre-processing steps includes data transformations with centering, scaling and missing value imputation. This ensures that the data quality steps are ensured during the training the model.


The trainControl() allows for the management of model evaluation criteria such as the resampling strategy  which is used in choosing the best model. This function can be used to modify by tuning two important parameters: method and selectionFunction.

The trainControl() function uses to set the resampling method, such as holdout sampling or k-fold cross-validation .The trainControl() parameter selectionFunction can be used to choose a function that can optimise the model’s performance.


The grid() function, which creates data frames from the combinations of all values setting such as model = "tree" and winnow = "FALSE" will optimise by searching eight different values of trials. The result of expand.grid()

Using the traincontrol () , grid() and parameter metric = "Kappa", indicating the statistic to be used by the model evaluation function. 


Bagging generates a number of training datasets by bootstrap sampling the original training data which are then used to generate a set of models using a single learning algorithm. The ipred package used for bagging () function for training and nbagg parameter is used to control number of decision tree voting in the ensemble.


Inspecting the evaluating matric, the Bagging model  a very slightly underperform as compare to previous models.
Random Forest is another method of ensemble models and championed by Leo Breiman and Adele Cutler . Random forest combines the base principles of bagging with random feature selection to add additional diversity to the decision tree models. After the ensemble of trees is generated, the model uses a vote to combine the trees' predictions. This model is trained through randomForest() function .

The Random Forest model can further optimise by setting up the tuning grid. The tuning parameter for this model is mtry, which defines how many features are randomly selected at each split. For the most accurate comparison of model performance use through repeated 10-fold cross-validation.


The models takes a much longer time and more computationally intensive to evaluate. It seems like training the model on these tuning parameter is quite hard to handle in randomForest package which has stopped working on the training.

The Random forest model is the best ensemble methods on optimising the Bank Marketing will yield better result on accuracy and kappa statistics.
