# Average Spread Predictor for Fruits & Vegetables

A machine learning project that predicts the **average price spread** of fruits and vegetables based on farm and city retail prices. This project includes a **Gradio web interface** for interactive predictions and logs all inputs and outputs for monitoring.

---

## Features

- Predict average spread for any fruit or vegetable using farm and city prices.
- Simple and interactive Gradio interface.
- Logs every input and prediction to `prediction_log.csv`.
- Calculates derived features (spread per city) automatically.

## Machine Learning Workflow

1. **Data Preprocessing**
   - Converted price and percentage columns to numeric types.
   - Extracted date features: `year`, `month`, `day`.
   - Created derived features
   - Handled missing 
2. **Feature Selection**
   - Target variable: `averagespread`
   - Input features:
     ```
     ['productname', 'farmprice', 'atlantaretail', 'chicagoretail',
      'losangelesretail', 'newyorkretail', 'year', 'month', 'day',
      'spread_atlanta', 'spread_chicago', 'spread_losangeles', 'spread_newyork']
     ```
3. **Train/Test Split**
   - 80% train, 20% test.

4. **Model Training**
   - RandomForestRegressor trained on the training set.

5. **Cross-Validation**
   - 5-fold cross-validation to evaluate stability.
   - Example results:
     ```
     Cross-Validation R² Scores: [0.9706, 0.9614, 0.9626, 0.9670, 0.9692]
     Mean CV R²: 0.9662
     ````
6. **Evaluation**
   - Metrics: MAE, MSE, R²
   - Example results:
     ```
     === Train Set ===
     MAE: 0.0443
     MSE: 0.0151
     R²: 0.9950

     === Test Set ===
     MAE: 0.1113
     MSE: 0.0690
     R²: 0.9769
     ```

7. **Prediction & Logging**
   - Gradio interface for interactive predictions.
   - All inputs and predicted outputs are logged in `prediction_log.csv`.
---

## Dataset

The model is trained on a dataset with the following columns:
['productname', 'farmprice', 'atlantaretail', 'chicagoretail',
'losangelesretail', 'newyorkretail', 'averagespread', 'year', 'month', 'day']

- `productname` includes fruits and vegetables like Strawberries, Romaine Lettuce, Potatoes, Oranges, etc.
- `averagespread` is the target variable.
- Additional derived features (`spread_` columns) are computed automatically in the app.

---

## Installation

1. Clone the repository:

```bash
git clone https://github.com/zaralrubaie/average-spread-predictor.git
cd average-spread-predictor
````
2. Install dependencies:
````
pip install -r requirements.txt
````
## Usage

Run the Gradio app:
````
fruit and veg data analysis
````
- Enter fruit or vegetable name, farm price, and city retail prices.

- Enter the date (year, month, day).

- Click Submit to get the predicted average spread.
  
## License

This project is licensed under the MIT License. See LICENSE file for details.
  

