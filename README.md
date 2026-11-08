Sales Prediction Using Python
CodeAlpha Internship --- Task 4

This project predicts product sales using advertising expenditure across
three channels: TV, Radio, and Newspaper. It compares Linear Regression
and Random Forest Regression models and evaluates their predictive
performance.
Project Objectives
- Explore the relationship between advertising budgets and sales.
- Clean and prepare the advertising dataset.
- Visualize correlations and advertising-channel relationships.
- Train and compare regression models.
- Identify the relative importance of advertising channels.
- Predict sales for a new advertising budget.
Dataset
File: Advertising.csv

The dataset contains 200 records and four analysis columns:

  Column        Description
  TV          Advertising budget spent on TV
Radio       Advertising budget spent on Radio
Newspaper   Advertising budget spent on Newspaper
Sales       Sales outcome

The original CSV also contains an Unnamed: 0 index column, which the
notebook removes. The dataset has no missing values in the inspected
file.
Methodology
1. Load the data: Read Advertising.csv using pandas.
2. Clean the data: Strip column-name whitespace, remove the
   unnecessary index column, remove duplicate rows, and drop missing
   values.
3. Define features and target: Use TV, Radio, and Newspaper
   as input features (X) and Sales as the target (y).
4. Explore relationships: Calculate correlations and create a
   heatmap and regression plots for each advertising channel.
5. Split the data: Use an 80:20 train-test split with
   random_state=42.
6. Train models:
   - Linear Regression
   - Random Forest Regressor with 200 estimators and
     random_state=42
7. Evaluate models: Compare Mean Absolute Error (MAE), Root Mean
   Squared Error (RMSE), and R² score.
8. Analyze feature importance: Use the Random Forest model's
   feature-importance values.
9. Predict a new case: Estimate sales for an advertising budget of
   TV = 200, Radio = 30, and Newspaper = 40.
Results
The supplied notebook reports the following test-set performance:

  Model                   MAE    RMSE   R² Score
  Linear Regression     1.461   1.782     0.8994
Random Forest         0.629   0.757     0.9818

The Random Forest model performs better on this particular train-test
split, with lower MAE and RMSE and a higher R² score.
Advertising Feature Importance
  Feature       Importance
  TV                 0.625
Radio              0.362
Newspaper          0.013

TV has the highest feature importance in the trained Random Forest
model, followed by Radio and Newspaper.
Example Prediction
For the new advertising budget:
- TV: 200
- Radio: 30
- Newspaper: 40
The notebook's Random Forest model predicts sales of 18.28 (in the
dataset's sales units).

These are the outputs recorded in the supplied notebook. Results may
vary if the data, split, or model settings change. Feature importance
describes the fitted model and should not be interpreted as proof of
causation.
Visualizations
The notebook generates and saves:
- correlation_heatmap.png
- advertising_impact.png
- feature_importance.png
Technologies Used
- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- Jupyter Notebook / Kaggle Notebooks
How to Run
Kaggle Notebooks
1. Upload or open sales-prediction-using-python.ipynb in Kaggle.
2. Add the Advertising.csv dataset.
3. Confirm the dataset path. The supplied notebook currently uses:
   df = pd.read_csv("/kaggle/input/datasets/riyadhdata262/advertising-dataset/Advertising.csv")
4. Update the path if your Kaggle dataset is located elsewhere.
5. Run all cells from top to bottom.
Run Locally
1. Keep the notebook and Advertising.csv in the same folder.
2. Install the dependencies:
   pip install numpy pandas matplotlib seaborn scikit-learn jupyter
3. Change the CSV-loading line to:
   df = pd.read_csv("Advertising.csv")
4. Start Jupyter:
   jupyter notebook
5. Open sales-prediction-using-python.ipynb and run all cells.
Project Structure
sales-prediction/
├── Advertising.csv
├── sales-prediction-using-python.ipynb
├── README.md
├── PROJECT_DESCRIPTION.md
├── correlation_heatmap.png
├── advertising_impact.png
└── feature_importance.png
The PNG files are generated when the notebook is executed.
Limitations and Future Improvements
- The dataset contains only 200 observations.
- Evaluation uses a single 80:20 train-test split; cross-validation
  could provide a more robust estimate.
- The project does not include hyperparameter tuning.
- The dataset does not establish causal effects of advertising
  expenditure.
- Future work could compare additional regression models, tune model
  parameters, and validate performance on new advertising data.

Author
Riyadh Hossain

Prepared for CodeAlpha Internship --- Task 4: Sales Prediction Using
Python.
