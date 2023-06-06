# Module-21-challenge
Deep-learning
The purpose of this report is to present the results of a deep neural network model for classifying successful charities for the Alphabet Soup charity. The model is based on preprocessing, compiling, training, and evaluating the data, with the goal of achieving an accuracy score of 0.75 or higher. The following steps were taken:

Preprocessing: Non-beneficial ID columns were dropped, and categorical data were converted into numerical values using pd.get_dummies. The initial model contained an input layer with 43 units, two hidden layers with 80 and 30 units, respectively, and an output layer with one unit.

Training: The model was trained using the "adam" optimizer, binary_crossentropy loss function, and accuracy metric. The training data was split into features and target arrays, and the features were scaled using StandardScaler. The model weights were saved every five epochs using ModelCheckpoint.

Hyperparameter Tuning: Different hyperparameters were tested using GridSearchCV and RandomSearchCV to achieve the target accuracy. The recommended hyperparameters from GridSearchCV include the 'relu' activation function, the 'adam' optimizer, and 80 units in the hidden layer. The recommended hyperparameters from RandomSearchCV include the 'sigmoid' activation function, the 'SGD' optimizer, and 8 hidden layers. Additional tests on the data showed that a learning rate of 0.1 and 100 epochs provided the highest level of accuracy for the dataset.

Optimization: Increasing the number of bins for the classification data to include all categories over 100 rather than 1000 increased the accuracy to 0.7310. However, increasing the number of bins for the application types to include all application types over 50 rather than 500 did not have any impact on the accuracy scores but reduced the loss score to 0.55.

Evaluation: The model's loss after training is 0.5678, and the accuracy is 0.7278. The inclusion of the hyperparameters recommended by GridSearchCV and RandomSearchCV increased the accuracy to 0.7282 and reduced the loss to 0.5653.

### Results
Target and Feature Variables
The target variable for the model is IS_SUCESSFUL, as this is what the model uses to identify the most likely parameters for success. The features used in the model include:

* APPLICATION_TYPE
* AFFILIATION
* CLASSIFICATION
* USE_CASE
* ORGANIZATION
* STATUS
* INCOME_AMT
* SPECIAL_CONSIDERATIONS
* ASK_AMT

#### Removed Variables
The variables EIN and NAME were removed from the input data as they are unique identifiers and do not benefit the model prediction abilities.

#### Model Architecture
The model has 8 layers, including an input layer, 6 hidden layers, and an output layer. The number of neurons in each layer are as follows: 80 for the input layer, 50 for the hidden layers, 30 for the last hidden layer, and 1 for the output layer. The activation function used for all hidden layers is ReLU, which is commonly used in deep learning networks for its ability to handle non-linear data and prevent the vanishing gradient problem. The activation function used for the output layer is sigmoid, which is commonly used for binary classification problems. These were selected based on recommendations by GridSearchCV and RandomSearchCV to try and reach an accuracy score of 75%.

#### Target Model Performance
The target model performance was not achieved, with the current accuracy score of the model being 73%.

#### Steps to Increase Model Performance
To increase model performance, various steps were taken, including:

#### Increase model performance
* Dropped non-beneficial ID columns and used binning to group low-frequency values in the 'APPLICATION_TYPE' and 'CLASSIFICATION' columns as "Other" during data preprocessing.
* Standardized the data using the StandardScaler for feature scaling.
* Used a deep neural network with multiple hidden layers to capture complex relationships in the data for model architecture.
* Used a ModelCheckpoint callback to save the weights of the model at certain intervals during training for callbacks.
* Tried different optimizers (Adam and SGD) to improve the training of the model for optimization.

Prior to using Gridsearch and other techniques, various learning rates and epochs, as well as a wider range of optimizers were experimented with.

### Summary
The Alphabet Soup Charity Report presents the results of a deep neural network model for classifying successful charities. The model is based on preprocessing, compiling, training, and evaluating the data, with the goal of achieving an accuracy score of 0.75 or higher. Steps taken to increase model performance include dropping non-beneficial ID columns, using binning to group low-frequency values, standardizing the data, using a deep neural network with multiple hidden layers, and trying different optimizers. The model's current accuracy score is 73%, and different hyperparameters were tested using GridSearchCV and RandomSearchCV to improve the accuracy score.
