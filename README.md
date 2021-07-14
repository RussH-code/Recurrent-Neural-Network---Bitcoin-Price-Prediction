# Recurrent-Neural-Network---Bitcoin-Price-Prediction

## What is time series forecasting
A time series is a series of data indexed in time order. It usually describes a sequence taken at successive equally spaced points in time. The order of the data matters and cannot be shuffled. Examples include stock price, temperature records and hormone cycles. 

Time series forecasting involves taking models fit on historical data and using them to extrapolate future observations. Here we will look at using deep learning to perform time series predictions. Other common methods usually include regression analysis with an auto-correlation term. 

## Recurrent Neural Network (RNN)

![](https://github.com/RussH-code/Recurrent-Neural-Network---Bitcoin-Price-Prediction/blob/main/RNN.png)

For time series predictions, we use the recurrent neural netowrk. RNN contains cycles that feed the network activations from a previous time steps as inputs to the network to influence predictions at the current time steps. These activations are stored as internal states. Classical RNN, however, suffers from vanishing/exploding (or both) gradient problem and fail to learn in the presence of time lags greater than 5 -10 discrete time steps. The influence of an input either decays or explodes exponentially as it cycles through the network. 

#### - LSTM
An improved model - "Long Short-Term Memory" (LSTM) was designed to solve this problem.  
