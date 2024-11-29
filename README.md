## README: House Sales Price Prediction Project

### **Project Overview**
RealAgents is a real estate company that seeks to optimize house sale prices to decrease time on the market. This project predicts house sale prices based on historical sales data. By analyzing and modeling the relationship between house characteristics and their sale prices, we aim to provide actionable insights to RealAgents for pricing strategy improvements.

---

### **Project Workflow**
1. **Data Cleaning**: Missing values in the dataset were addressed based on predefined rules to ensure data quality.
2. **Exploratory Data Analysis (EDA)**: Key patterns and statistics, such as the impact of bedroom count on price, were explored.
3. **Modeling**: Two predictive models, a baseline Linear Regression model and a comparison Random Forest model, were implemented.
4. **Evaluation**: Models were evaluated on their prediction accuracy using RMSE (Root Mean Squared Error).

---

### **Dataset Details**
The project uses three datasets:
1. `house_sales.csv` - Historical sales data for analysis and cleaning.
2. `train.csv` - Training data for model fitting.
3. `validation.csv` - Data for testing and generating predictions.

#### **Dataset Columns**
| Column Name     | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| house_id         | Unique identifier for houses.                                              |
| city             | City where the house is located ('Silvertown', 'Riverford', etc.).         |
| sale_price       | Sale price of the house in dollars.                                        |
| sale_date        | Date of the last sale.                                                     |
| months_listed    | Number of months the house was on the market.                              |
| bedrooms         | Number of bedrooms in the house.                                           |
| house_type       | Type of house ('Terraced', 'Semi-detached', 'Detached').                   |
| area             | Area of the house in square meters.                                        |

---

### **Steps and Methods**

#### **1. Data Cleaning**
The dataset contained missing or erroneous values, which were addressed as follows:
- **City**: Missing entries replaced with "Unknown".
- **Sale Price**: Missing or non-positive values removed.
- **Sale Date**: Missing values replaced with `2023-01-01`.
- **Months Listed**: Missing values replaced with the column mean, rounded to 1 decimal place.
- **Bedrooms**: Missing values replaced with the column mean, rounded to the nearest integer.
- **House Type**: Missing values replaced with the most common house type.
- **Area**: Missing values replaced with the column mean, rounded to 1 decimal place.

#### **2. Exploratory Data Analysis (EDA)**
To validate assumptions:
- Average price and variance were analyzed by bedroom count to determine its influence on sale prices.
- Results were displayed in a table (`price_by_rooms`), showing average price (`avg_price`) and variance (`var_price`) rounded to 1 decimal place.

#### **3. Modeling**
- **Baseline Model**: A Linear Regression model was trained on the `train.csv` dataset.
- **Comparison Model**: A Random Forest Regressor was implemented as a more robust predictive model.
- **Feature Engineering**: Sale dates were split into year, month, and day to add temporal features to the model.

#### **4. Evaluation**
Model performance was compared using RMSE:
- **Baseline Model RMSE**: 22,814
- **Comparison Model RMSE**: 14,549  
The Random Forest model demonstrated superior predictive performance.

---

### **Results**
#### **Baseline Model Predictions**
The baseline model's predictions for the `validation.csv` dataset are saved in `base_result` with the following structure:
| house_id | price          |
|----------|----------------|
| 1331375  | 122,123.37     |
| ...      | ...            |

#### **Comparison Model Predictions**
The Random Forest model's predictions are saved in `compare_result` with the following structure:
| house_id | price          |
|----------|----------------|
| 1331375  | 82,007.62      |
| ...      | ...            |

---

### **How to Use**
1. Clone this repository:  
   ```bash
   git clone https://github.com/myslyurt/House-sales-prediction-Data-scientist-associate-cert-project.git
   cd House-sales-prediction-Data-scientist-associate-cert-project
   ```

2. Install required Python libraries:  
   ```bash
   pip install -r requirements.txt
   ```

3. Run the code to reproduce the workflow:
   ```bash
   python main.py
   ```

4. Access model predictions:
   - Baseline model: `base_result.csv`
   - Comparison model: `compare_result.csv`

---

### **Key Files**
- `house_sales.csv`: Source data with historical house sales.
- `train.csv` and `validation.csv`: Training and validation datasets for model fitting.
- `main.py`: Main script to clean data, train models, and generate predictions.
- `README.md`: Project documentation (this file).

---

### **Future Work**
- **Feature Expansion**: Incorporate additional features like neighborhood data or nearby amenities.
- **Hyperparameter Tuning**: Optimize the Random Forest model for better performance.
- **Advanced Models**: Explore gradient boosting techniques (e.g., XGBoost, LightGBM) for further accuracy.

---

### **Contact**
If you have any questions or suggestions, please contact:
- **Name**: Murat Yesilyurt
- **Email**: myesilyurtdsc@gmail.com
- **Linkedin**: [Murat Yesilyurt](https://www.linkedin.com/in/yesilyurt-murat/)
- 

Happy coding! 😊
