# Stock_prediction_RNN
This RNN Deals with the Prediction of opening of the market for a particular company (here, i.e. TATA sponge)  

# INTRODUCTION
Welcome to the Stock_prediction_RNN wiki! We used last 10 years data for TATA sponge from investment.com to predict the opening stocks of the company. The training data i.e. `TATA_Stock_Price_Train.csv` were trained in such a way that for each prediction of the opening data It will take previous 60 data point which i nothing but previous 60 days opening data.

The input size of the matrix is 3 dimensional here (1197,60,1) which is done for the convenience of the predictor to add more companies data of same no. of data points and same dates which are highly correlated with the company which is of your interest.

# REPROCESSING and MODEL CREATION
## REPROCESSING
As most of you already know that NN generally required normalized and scaled data because Reducing the scale of the target variable will, in turn, reduce the size of the gradient used to update the weights and result in a more stable model and training process.A natural method for rescaling the variable would be to standardize the variable. There are number of methods to do that so like max-min method which is used here.

## MODEL CREATION
We will create a RNN model with: 
**1.** First LSTM layer and some Dropout regularisation
**2.** Second LSTM layer and some Dropout regularisation 
**3.** Third LSTM layer and some Dropout regularisation 
**4.** Fourth LSTM layer and some Dropout regularisation 
**5.** Output layer with single output

**WE ARE COMPILING THE MODEL USING `adam` OPTIMIZER AND MEAN SQUARED ERROR AS LOSS FUNCTION.**

# TESTING
As we are using previous 60 data points for prediction the next data points,In test data obtained from `TATA_Stock_Price_Test.csv` for predicting first 60 data points we need to concat previous 60 points from the training data i.e. `TATA_Stock_Price_Train.csv`. There are total 20 data points on which prediction were made but for next data we are using real data instead of predicted data as the confidence of prediction will decrease.

**GRAPHICLA REPRESENTATION**
![]Capture.PNG
