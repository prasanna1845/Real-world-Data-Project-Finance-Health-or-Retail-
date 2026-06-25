# Real-world-Data-Project-Finance-Health-or-Retail-

🔴 DESCRIPTION 

1. Importing Libraries
The program starts by importing the required Python libraries:
Pandas – Loads and manages the dataset.
Matplotlib – Creates graphs and visualizations.
Scikit-learn – Builds and evaluates the machine learning model.
Python
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score

2. Loading the Dataset
The retail sales dataset is loaded from a CSV file into a DataFrame.
Python
data = pd.read_csv("retail_sales.csv")

3. Displaying and Checking the Data
The first few rows of the dataset are displayed, and missing values are identified.
Python
print(data.head())
print(data.isnull().sum())

4. Data Cleaning
Missing values are removed to ensure accurate analysis.
Python
data = data.dropna()

5. Date Conversion
The Date column is converted into datetime format for time-based analysis.
Python
data['Date'] = pd.to_datetime(data['Date'])

6. Sales Analysis
Monthly sales are calculated by grouping sales according to the month.
Python
monthly_sales = data.groupby(data['Date'].dt.month)['Sales'].sum()

7. Data Visualization
A bar chart is created to show monthly sales performance.
Python
monthly_sales.plot(kind='bar')
Purpose: Helps identify sales trends and compare monthly performance.

8. Feature Selection
The model uses Quantity as the input feature and Sales as the target variable.
Python
X = data[['Quantity']]
y = data['Sales']

9. Splitting the Dataset
The dataset is divided into training data (80%) and testing data (20%).
Python
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

10. Model Training
A Linear Regression model is created and trained using the training dataset.
Python
model = LinearRegression()
model.fit(X_train, y_train)

11. Prediction
The trained model predicts sales for the test dataset.
Python
y_pred = model.predict(X_test)

12. Model Evaluation
The model performance is measured using:
Mean Squared Error (MSE): Measures prediction error.
R² Score: Indicates how well the model fits the data.
Python
print("Mean Squared Error:", mean_squared_error(y_test, y_pred))
print("R2 Score:", r2_score(y_test, y_pred))

13. Prediction Graph
A scatter plot compares the actual sales with the predicted sales.
Python
plt.scatter(y_test, y_pred)
Purpose: Shows how closely the predicted values match the actual values.

OUTPUT 📌

<img width="500" height="500" alt="Image" src="https://github.com/user-attachments/assets/cd4274f6-c944-48a6-8920-6cd7f757b4de" />

<img width="600" height="400" alt="Image" src="https://github.com/user-attachments/assets/acdc75f8-172e-4190-88e1-fd2298a443c8" />

<img width="4800" height="2800" alt="Image" src="https://github.com/user-attachments/assets/710e47a8-491b-4bb4-a183-977fe56aac72" />
