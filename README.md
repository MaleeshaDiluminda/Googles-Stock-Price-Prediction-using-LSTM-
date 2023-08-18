# Googles-Stock-Price-Prediction-using-LSTM-
Googles Stock Price Prediction using LSTM 

![m-blog-2](https://github.com/MaleeshaDiluminda/Googles-Stock-Price-Prediction-using-LSTM-/assets/61634241/9c79f843-f834-40d8-9d92-f0f29c72080a)

This project is about Google’s stock price prediction using Keras’ LSTM model trained on past stock data.

have got the data set from Kaggle the data set contains 2012 to 2017 Google stock price data and the data set contains information such as the date, opening price, closing price, highest price, lowest price, and trading volume.

I considered LSTM, random forest, and Artificial neural networks to use as machine learning techniques for this Google stock price prediction, And I chose to use LSTM because LSTM is able to learn long short-term dependencies in the data and handle the missing data which makes them more suitable for stock price prediction than random forest and Artificial neural networks.

First, I have imported the required libraries such as numpy, pandas, matplotlib

![image](https://github.com/MaleeshaDiluminda/Googles-Stock-Price-Prediction-using-LSTM-/assets/61634241/28cdff4b-0b00-4e8b-acb5-2d7d30b875a1)


This code block is used to read the training data, I’m just taking the first column here which is the open column in the data set. Then I initialized the MinMaxScaler to scale the data between 0 and 1. After that, I initialized two arrays called x_train and y_train. The first entry in the x_train array is the first 60 open stock prices and the first entry in the y_train is the 61st value of open stock price. I have done that because I want the model to predict the 61st value of stock price when I provide it with the previous 60 values. In this way, we can keep on building X_train and y_train.

![image](https://github.com/MaleeshaDiluminda/Googles-Stock-Price-Prediction-using-LSTM-/assets/61634241/3861917f-20a6-4101-8767-8f7a177e6a68)


And the 3rd step is getting the training data in shape here I have converted the lists to arrays and in the second step I added dummy dimensions in the end because kernel models require the data in this format only.

![image](https://github.com/MaleeshaDiluminda/Googles-Stock-Price-Prediction-using-LSTM-/assets/61634241/dbdb6339-f6fd-4d41-b18d-efcfa0141f0e)


The 4th step is creating the stock price prediction model and this sequential model consists of 4 LSTM layers with 50 units each. After these LSTM layers here we can see a dense layer. I used Adam optimizer here and for the loss, I used mean squared error

LSTM

This layer uses available constraints and runtime hardware to gain the most optimized performance

Why dense is used in Python?

Dense is the only actual network layer in that model. A Dense layer feeds all outputs from the previous layer to all its neurons, each neuron providing one output to the next layer. It’s the most basic layer in neural networks.

Adam is an optimization algorithm that can be used instead of the classical stochastic gradient descent procedure to update network weights iterative based on training data.

Mean Squared Error measures how close a regression line is to a set of data points.

![image](https://github.com/MaleeshaDiluminda/Googles-Stock-Price-Prediction-using-LSTM-/assets/61634241/bc11ab80-8ca9-4b35-ac39-9de401383820)


The 5 th step is Training the Stock Price Prediction model. here I trained our model for 100 epochs, and the batch size I have taken is 32 ( you can also experiment with these values )

![image](https://github.com/MaleeshaDiluminda/Googles-Stock-Price-Prediction-using-LSTM-/assets/61634241/308bb4cb-7492-44cd-9b6a-805b56ae441e)


Step 6 is reading the test data.

![image](https://github.com/MaleeshaDiluminda/Googles-Stock-Price-Prediction-using-LSTM-/assets/61634241/e5dd5e60-c3f2-42a4-9189-d6d9d8829fa1)


Step 7 is getting the stock price predictions on test data, In here I concatenated the test open column with the train open column row-wise. The step I did above was just to take the last 60 values from the train data and also add that data to the test data, then reshape it to have just one column and as many rows, and scale it using MinMaxScaler then created the test data as did for the training data, from here we can make predictions.

Basically What we are doing here first taking the last 60 open values from the train and making predictions from it for the 61st value. Then what we will do is we will drop the 0th open value and now the input array will be 1st open value to the 61st open value (60 values) and will predict the 62nd open value and like this, we can keep on predicting the next value and take that for predicting next values.

![image](https://github.com/MaleeshaDiluminda/Googles-Stock-Price-Prediction-using-LSTM-/assets/61634241/ec5d5c0b-21a1-493e-a121-3fa2eb9d1455)


And this is the last step here we are plotting the predictions and real data our predictions are in the blue curve and the red curve represents its true value which means what it should be exactly, and you can see my model is not that perfect but still it is capable of catching the spikes with real google stock price it has the shape.

![image](https://github.com/MaleeshaDiluminda/Googles-Stock-Price-Prediction-using-LSTM-/assets/61634241/fcff7c86-c133-430e-ab43-efcbd065a506)

GIT Hub Link: https://github.com/MaleeshaDiluminda/Googles-Stock-Price-Prediction-using-LSTM-

