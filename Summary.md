# LSTM-Stock-Predictor
In this assignment, I was asked to build and evaluate deep learning models using both the FNG values and simple closing prices to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data. To do this,  I  use deep learning recurrent neural networks to model bitcoin closing prices. I use 2  models  for for the  preditions 
1.  FNG indicators to predict the closing price 
2.  Window of closing prices to predict the nth closing price.

## I. Methodology 
I followed the following Methidologies: I first prepare the data for training and testing, then I build and train custom LSTM RNNs, finally I evaluate the performance of each model. 

## II. Data Prep for Training and Testing
I use  FNG values to predict future closing prices and  past closing prices to predict future closing prices.  I apply the MinMaxScaler to the X and Y values to scale the data for the model. Then I reshape X_train and X_test to fit the model requirements. 

 ## III. Training the Model
Once the model is defined, I  train (fit) the model using 10 epochs. Since I am  working with time-series data, it's important to set shuffle=False since it's necessary to keep the sequential order of the data. 

## IV. Models Performance: FNG model vs the closing price model
1. In this section, we evaluate the model using the test data. closing price model perfroms better for it has the lowest loss 0.0651  compared to 0.1290 for FNG Model

*   LSTM RNN closing price loss:  0.0651 
*   FNG model loss = 0.1290

2. LSTM RNN  tracks the actual values best over time. the actiual value is consistent with predicted values. FNG model has high predicted values (twice the real value) and it is more linear. 


3. For both models, I use epochs = 10 and batch_size = 1. Having the batch_size = 1, helps to see  better how both models are  performing.I  experiment with the batch_size parameter ( 1-30 and 90);  smaller batch size is use (1)  Then, I experiement the Window size performance 1 through 10 to see how well the models will  perform. I come to the following conclusion: 
* FNG model -   The higher the window size the better the loss 
* LSTM RNN - The lower the window size,  the higher  the loss.

