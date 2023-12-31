# Bitcoin-Prediction

This repository is dedicated to the bitcoin prediction. The phase of the prediction is the data extraction which for this project I used the the API that provided by https://www.cryptocompare.com/. Below I have added the top 5 responses which taken from the API:

![Screenshot from 2020-02-05 22-04-39](https://user-images.githubusercontent.com/23243761/73883512-5cdae400-4864-11ea-925e-e34c57f6b07f.jpg)

After taking the required information from the API which varies from 2014 to 2020, I took this dataset and devided into 80% as the training test and 20% as the validation/test(10% validation and 10% test).At below figure you could see the behaviour of the timeseries that we are working on: 
![BitCoinPrice_USD_OverTime](https://user-images.githubusercontent.com/23243761/73881560-d5d83c80-4860-11ea-8bba-b2262399d611.png)

For training the LSTM, the data was split into windows of 7 days (this number is arbitrary, I simply chose a week here) and within each window I normalised the data to zero base, i.e. the first entry of each window is 0 and all other values represent the change with respect to the first value. Hence, I am predicting price changes, rather than absolute price.I used a simple neural network with a single LSTM layer consisting of 20 neurons, a dropout factor of 0.25, and a Dense layer with a single linear activation function. In addition, I used Mean Absolute Error (MAE) as loss function and the Adam optimiser.
The LSTM model is as below:

![model_plot](https://user-images.githubusercontent.com/23243761/73882005-a8d85980-4861-11ea-8672-9ef3562d4415.png)

once the model creation and prediction done we could see that the actual value and the predicted one are quite similar to each other: 
![Predicted_VS_Actual](https://user-images.githubusercontent.com/23243761/73882518-8430b180-4862-11ea-83a0-2209ba4b34c2.png)
