Income–Expense Prediction Model

This project is a machine learning web application that predicts expenses based on income and age using Linear Regression. The model is trained on a dataset (Income_Expense_Data.csv), processed, and deployed through a Flask web app with a simple web interface.

 Features

Data preprocessing and cleaning (handling missing values, outliers).

Exploratory Data Analysis (EDA) with plots and correlation heatmap.

Feature scaling using MinMaxScaler.

Linear Regression model for expense prediction.

Flask-based web application with a user-friendly interface (index.html).

REST API support for prediction using JSON requests.
Project Structure
bash
├── model.pkl                # Saved Linear Regression model  
├── app.py                   # Flask application  
├── Income_Expense_Data.csv  # Dataset used for training  
├── templates/
│   └── index.html           # Frontend for web input/output  
└── README.md                # Project documentation  

Installation

Clone the repository or copy project files to your machine.

Install required Python packages:
bash 
pip install flask numpy pandas scikit-learn matplotlib seaborn
Usage
1. Train the Model

The training script cleans the data, handles missing values/outliers, performs scaling, and trains a Linear Regression model.
The trained model is saved as model.pkl using pickle:
python
import pickle
pickle.dump(model, open('model.pkl','wb'))
2. Run Flask App

Start the Flask server:
bash
python app.py

The app will run on:

http://0.0.0.0:8080/   (local browser)
Web Interface

Open the app in your browser.

Enter Income and Age values.

The app will display:
Expense = <predicted_value>
API Endpoint

You can also send a JSON request for predictions:

POST Request:
python
import requests

url = 'http://localhost:5000/results'
r = requests.post(url, json={'rate':5, 'sales_in_first_month':200, 'sales_in_second_month':400})
print(r.json())
Model Accuracy

The model achieves:

R² score (accuracy on test data): ~ (depends on dataset split)

Predictions are scaled back for interpretability.

Technologies Used

Python

Flask

Pandas, NumPy

Scikit-learn

Matplotlib, Seaborn

Next Steps

Improve model performance using advanced regression techniques.

Deploy on cloud platforms (Heroku, AWS, or Docker).

Enhance frontend UI with Bootstrap/React.
