# 🛒 Retail Sales Forecasting & Dashboarding

## 📌 Project Overview
This project is an end-to-end data analysis and machine learning solution designed to predict store sales for a large grocery retailer. By analyzing historical sales, oil prices, holiday events, and store metadata, the model generates a **30-day sales forecast** to assist in inventory planning and demand forecasting.

The final output is an interactive **Power BI Dashboard** that allows stakeholders to visualize future trends, regional performance, and top-selling product categories.

## 🚀 Business Goal
To predict store sales accurately for the next 30 days, enabling better inventory management and reducing stockouts or overstock situations.

## 🛠️ Tech Stack
* **Language:** Python (v3.11.0)
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn
* **Visualization:** Power BI Desktop
* **Environment:** Jupyter Notebook / Google Colab

## 📂 Dataset
The data includes daily sales records, store metadata, oil prices, and holiday events.
* `train.csv`: Historical sales data (dates, store_nbr, product family, sales).
* `holidays_events.csv`: National and local holidays.
* `stores.csv`: Metadata (city, state, store type).

## ⚙️ Project Architecture
The project follows a standard ETL and Machine Learning pipeline:

1.  **Data Ingestion & Merging:**
    * Combined multiple CSV files (sales, holidays, stores) into a single analytical dataset.
    * Handled missing values (e.g., filling missing oil prices using backfill).
2.  **Feature Engineering:**
    * **Date Features:** Extracted day, month, year, day of week, and weekend flags.
    * **Lag Features:** Created lag variables (previous day's sales) to capture temporal dependencies.
    * **Rolling Averages:** Calculated 7-day moving averages to smooth out noise.
3.  **Machine Learning:**
    * Model: **Linear Regression** (Baseline model for trend forecasting).
    * Training: Trained on historical data to learn the relationship between time features and sales.
4.  **Forecasting:**
    * Generated predictions for the next 30 days ("Future Data").
5.  **Dashboarding (Power BI):**
    * Exported cleaned historical data and forecast data to CSV.
    * Built a dashboard featuring:
        * **KPIs:** Total Historical Sales vs. Forecasted Revenue.
        * **Hero Visual:** Line chart comparing historical trends vs. predicted future path.
        * **Geospatial Analysis:** Map visualization of sales by state.
        * **Category Performance:** Top 5 performing product families.

## 📊 Power BI Dashboard

The dashboard connects to the processed CSV outputs (`final_forecast_for_powerbi.csv` and `historical_sales_granular.csv`) to provide an interactive view of the data.

## 📝 How to Run
1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Vishal07238/Sales_Forcasting_Project.git
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn
    ```
3.  **Run the analysis:**
    * Open the Jupyter Notebook (`sales_forecasting.ipynb`).
    * Run all cells to process data, train the model, and generate forecast CSVs.
4.  **View the Dashboard:**
    * Open `Sales_Dashboard.pbix` in Power BI Desktop.
    * Refresh data to load the latest CSV outputs.

## 📈 Future Improvements
* Experiment with advanced models like **XGBoost** or **Prophet** for better seasonality capture.
* Integrate `onpromotion` data more deeply to analyze marketing impact.
* Deploy the model as a Flask API for real-time inference.
