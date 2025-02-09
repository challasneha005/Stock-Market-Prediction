# Stock Market Prediction and Forecasting using LSTM

## Overview
This project implements a stock market prediction model using Long Short-Term Memory (LSTM) neural networks. The model is trained on historical stock price data to forecast future stock prices.

## Dataset Collection
- The stock data is fetched using the Tiingo API for Apple Inc. (AAPL).
- Data is saved in `Stock.csv` and preprocessed for training.
- The dataset includes the `close` prices of the stock.

## Dependencies
Ensure the following Python libraries are installed:
```sh
pip install requests pandas numpy matplotlib scikit-learn tensorflow pandas-datareader
```

## Data Preprocessing
- The dataset is loaded and transformed using MinMaxScaler to normalize the stock prices.
- The dataset is split into training (65%) and testing (35%) sets.
- A sliding window approach is used to create sequences for training the LSTM model.

## Model Architecture
- **LSTM Layers**: Three stacked LSTM layers with 50 units each.
- **Dense Output Layer**: A single neuron to predict stock prices.
- **Loss Function**: Mean Squared Error (MSE).
- **Optimizer**: Adam.

## Training
- The model is trained for 100 epochs with a batch size of 64.
- Training and validation data are used to monitor performance.

## Performance Evaluation
- Root Mean Squared Error (RMSE) is calculated for both train and test datasets.
- The predicted stock prices are visualized using Matplotlib.

## Future Predictions
- The model forecasts stock prices for the next 30 days using the last known stock prices as input.
- The predicted values are plotted alongside actual stock prices for visualization.

## Running the Model
1. Fetch stock data from the Tiingo API.
2. Preprocess the dataset and split it into train/test sets.
3. Train the LSTM model using:
```python
model.fit(X_train, y_train, validation_data=(X_test, y_test), epochs=100, batch_size=64, verbose=1)
```
4. Evaluate the model performance:
```python
math.sqrt(mean_squared_error(y_test, test_predict))
```
5. Forecast future stock prices and visualize the results.
 
🤝 Contributing

Feel free to open an issue or submit a pull request!
