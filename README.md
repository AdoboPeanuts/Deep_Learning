# LSTM Stock Predictor by John Mangahas

![deep-learning.jpg](Images/deep-learning.jpg)

Due to the volatility of cryptocurrency speculation, investors will often try to incorporate sentiment from social media and news articles to help guide their trading strategies. One such indicator is the [Crypto Fear and Greed Index (FNG)](https://alternative.me/crypto/fear-and-greed-index/) which attempts to use a variety of data sources to produce a daily FNG value for cryptocurrency. You have been asked to help build and evaluate deep learning models using both the FNG values and simple closing prices to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data.

In this assignment, I will use deep learning recurrent neural networks to model bitcoin closing prices. One model will use the FNG indicators to predict the closing price while the second model will use a window of closing prices to predict the nth closing price.

Key Objectives:

1. [Prepare the data for training and testing](#prepare-the-data-for-training-and-testing)
2. [Build and train custom LSTM RNNs](#build-and-train-custom-lstm-rnns)
3. [Evaluate the performance of each model](#evaluate-the-performance-of-each-model)

- - -

### Files

[Closing Prices Starter Notebook](lstm_stock_predictor/lstm_stock_predictor_closing.ipynb)

[FNG Starter Notebook](lstm_stock_predictor/lstm_stock_predictor_fng.ipynb)

- - -

## Process and Workflow

### Prepared the data for training and testing

1. Used the starter code as a guide to create a Jupyter Notebook for each RNN. The starter code contains a function to create the window of time for the data in each dataset.

2. For the Fear and Greed model, I used the FNG values to try and predict the closing price. A function is provided in the notebook to help with this.

3. For the closing price model, I used previous closing prices to try and predict the next closing price. A function is provided in the notebook to help with this.

4. Each model will need to use 70% of the data for training and 30% of the data for testing.

5. Apply a MinMaxScaler to the X and y values to scale the data for the model.

6. reshape the X_train and X_test values to fit the model's requirement of samples, time steps, and features. (*example:* `X_train = X_train.reshape((X_train.shape[0], X_train.shape[1], 1))`)

### Build and train custom LSTM RNNs

Created the same custom LSTM RNN architecture. Fitted the data using the FNG values.

Used the same parameters and training steps for each model. 

### Evaluate the performance of each model

Used the testing data to evaluated each model and compared the performance.

Results:

> Which model has a lower loss? 

## The closing price model has the lower loss on the test data - RMSE of 0.0078 vs 0.0696.

> Which model tracks the actual values better over time?

## Closing price model tracks the actual values better over time. Based on the graph, closing prices versus the FNG values shows a very low correlation.

> Which window size works best for the model?

# Window size should be lower than 10 so get a more accurate information.

- - -

### Resources

[Keras Sequential Model Guide](https://keras.io/getting-started/sequential-model-guide/)

[Illustrated Guide to LSTMs](https://towardsdatascience.com/illustrated-guide-to-lstms-and-gru-s-a-step-by-step-explanation-44e9eb85bf21)

[Stanford's RNN Cheatsheet](https://stanford.edu/~shervine/teaching/cs-230/cheatsheet-recurrent-neural-networks)

- - -

