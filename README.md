# Recurrent Neural Network - Bitcoin Price Prediction

# What is time series forecasting
A time series is a series of data indexed in time order. It usually describes a sequence taken at successive equally spaced points in time. The order of the data matters and cannot be shuffled. Examples include stock price, temperature records and hormone cycles. 

Time series forecasting involves taking models fit on historical data and using them to extrapolate future observations. Here we will look at using deep learning to perform time series predictions. Other common methods usually include regression analysis with an auto-correlation term. 

## Recurrent Neural Network (RNN)

![](https://github.com/RussH-code/Recurrent-Neural-Network---Bitcoin-Price-Prediction/blob/main/RNN.png)

Source: <a href="https://en.wikipedia.org/wiki/Recurrent_neural_network">Recurrent Neural Network - Wikipedia</a>

For time series predictions, we use the recurrent neural netowrk. RNN contains cycles that feed the network activations from a previous time steps as inputs to the network to influence predictions at the current time steps. These activations are stored as internal states. Classical RNN, however, suffers from vanishing/exploding (or both) gradient problem. During gradient update, the weight is updated as such:

**new weight = weight - learning rate * gradient**

So layers that receive small gradient update does not learn, and those that recieve a big updates fail to converge. The influence of an input either decays or explodes exponentially as it cycles through the network. This usually happens in RNN in the earlier layers during back propagation. Therefore, RNN usualy fails to learn properly in the presence of time lags greater than 5 -10 discrete time steps. 

#### - LSTM
![](https://github.com/RussH-code/Recurrent-Neural-Network---Bitcoin-Price-Prediction/blob/main/LSTM.png)

Source: Colah's blog - <a href="https://colah.github.io/posts/2015-08-Understanding-LSTMs/">Understanding LSTM Networks</a>

An improved model - "Long Short-Term Memory" (LSTM) was designed to solve this problem. What makes LSTM special is its cell state and gates. The cell state acts like the memory of the network, and transfers information down the sequence chain. This allows information from earlier time steps to reach later time steps, and reduce effect of short-term memory. Gates control what information to keep or forget by learning the relevant information. This is achieved by activation function. A sigmoid activation squishes values between 0 (forgotten) and 1 (kept), this helps update the states.

## Processing Time Series Data
Given a time series data, how do we generate features (x) and labels (y)? Here we use the sliding window technique. We determine a set sequence length for each inputs (e.g. 10). Then we use data at time x till time x + 10 to predict data at time x + 11. The following figure summarises the procedure.


