# Product Demand Forecasting

An end-to-end machine learning project that predicts product demand using historical retail data (pricing, discounts, inventory, promotions, weather, and seasonality). The project covers exploratory data analysis, feature engineering, model training (XGBoost), and deployment as an interactive Streamlit web app.

## Demo

The app takes in product/store features and returns a predicted demand (in units), so retailers can make more informed decisions on inventory and pricing.

## Project Objective

To develop an end-to-end demand forecasting solution that leverages machine learning and time series analysis to predict customer demand, evaluate model performance, and provide actionable insights for inventory management and business operations.

## Dataset

The dataset contains 76,000 records with 16 features, including:

| Feature | Description |
|---|---|
| Date | Date of the record |
| Store ID / Product ID | Identifiers |
| Category | Product category (Electronics, Clothing, Groceries, etc.) |
| Region | Sales region |
| Inventory Level | Units in stock |
| Units Sold / Units Ordered | Sales and order volumes |
| Price / Discount | Product pricing and discount percentage |
| Weather Condition | Weather at time of sale |
| Promotion | Whether a promotion was active (0/1) |
| Competitor Pricing | Competitor's price for the same product |
| Seasonality | Season (Winter, Summer, etc.) |
| Epidemic | Whether an epidemic-affected period (0/1) |
| Demand | Target variable — units in demand |

## Workflow

1. **Data Cleaning & EDA** — checked for missing values and duplicates, examined data types, and explored distributions.
2. **Feature Engineering** — extracted `Year`, `Month`, `Day`, and `Weekday` from the date; derived `Discounted Price` and `Sell-through Rate`.
3. **Business & Visual Insights** — analyzed demand trends across category, region, seasonality, promotions, and weather using grouped statistics and visualizations (histograms, boxplots, scatterplots, bar charts, time series plots).
4. **Preprocessing** — encoded categorical variables and exported a clean dataset (`preprocessed_data.csv`) for modeling.
5. **Model Training** — trained an XGBoost regression model on the processed features to predict demand.
6. **Deployment** — built an interactive Streamlit app for real-time demand prediction from user-provided inputs.

## Tech Stack

- **Language:** Python
- **Data Analysis:** pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Modeling:** XGBoost, scikit-learn (Label Encoding)
- **Deployment:** Streamlit

## Repository Structure

```
├── analysis.ipynb           # EDA, feature engineering, and business insights
├── app.py                   # Streamlit app for demand prediction
├── xgboost_demand_model.pkl # Trained XGBoost model
├── label_encoder.pkl        # Fitted label encoders for categorical features
└── README.md
```

> **Note:** The model training/preprocessing notebook that produces `xgboost_demand_model.pkl` and `label_encoder.pkl` is not yet included in this repo. It will be added soon.

## How to Run Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```

2. Install dependencies:
   ```bash
   pip install streamlit pandas numpy scikit-learn xgboost
   ```

3. Run the Streamlit app:
   ```bash
   streamlit run app.py
   ```

4. Open the local URL shown in the terminal (usually `http://localhost:8501`) in your browser.

## App Features

The app accepts the following inputs and returns a predicted demand:

- Price
- Discount (%)
- Inventory Level
- Promotion (0/1)
- Competitor Pricing
- Category

## Future Improvements

- Add the missing preprocessing/model-training notebook to the repo
- Replace hardcoded local file paths in `app.py` with relative paths so the app runs on any machine (see note below)
- Incorporate time-series-specific models (e.g., Prophet, SARIMA) to capture seasonality more explicitly
- Add model evaluation metrics (RMSE, MAE, R²) to the README once training results are finalized
- Deploy the app publicly (e.g., Streamlit Community Cloud)

## Author

**Mehedee Hasan Nyeem**
Data Analyst | Data Science Student
