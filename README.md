# Average Spread Predictor for Fruits & Vegetables

A machine learning project that predicts the **average price spread** of fruits and vegetables based on farm and city retail prices. This project includes a **Gradio web interface** for interactive predictions and logs all inputs and outputs for monitoring.

---

## Features

- Predict average spread for any fruit or vegetable using farm and city prices.
- Simple and interactive Gradio interface.
- Logs every input and prediction to `prediction_log.csv`.
- Calculates derived features (spread per city) automatically.

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
git clone https://github.com/your-username/average-spread-predictor.git
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

- All predictions are logged automatically in prediction_log.csv.
  
## Example 
| Product Name    | Farm Price | Atlanta | Chicago | Los Angeles | New York | Year | Month | Day | Predicted Spread |
| --------------- | ---------- | ------- | ------- | ----------- | -------- | ---- | ----- | --- | ---------------- |
| Strawberries    | 1.16       | 2.23    | 1.70    | 1.99        | 2.54     | 2019 | 5     | 19  | 0.8233           |
| Romaine Lettuce | 0.35       | 1.72    | 2.00    | 1.69        | 1.99     | 2019 | 5     | 19  | 4.2857           |
