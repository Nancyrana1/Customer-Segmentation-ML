# Customer Segmentation using K-Means Clustering

A machine-learning project that groups mall customers based on their **annual income** and **spending score**. The repository includes an exploratory Jupyter notebook, a trained clustering model, and a Flask web application that accepts customer data in CSV format and returns predicted cluster assignments.

## Project Overview

Customer segmentation helps businesses understand groups of customers with similar characteristics. This project uses the K-Means clustering algorithm to assign customers to clusters using two features:

- **Annual Income (k$)**
- **Spending Score (1–100)**

The provided Flask application loads the saved model, accepts a CSV upload containing those columns, predicts a cluster for each row, and displays the resulting data as an HTML table.

## Features

- Explore the mall customer dataset in a Jupyter notebook.
- Use a saved K-Means model for clustering predictions.
- Upload a CSV file through a simple web interface.
- View the uploaded customer records with their predicted `Cluster` labels.

## Tech Stack

- **Python** – project and backend programming language
- **Pandas** – CSV loading and tabular data handling
- **NumPy** – numerical computing
- **scikit-learn** – machine-learning model and clustering
- **Flask** – web application and prediction endpoint
- **HTML and CSS** – upload interface
- **Jupyter Notebook** – model exploration and experimentation
- **Pickle** – loading the saved model

The application also uses the supporting Python packages listed in `requirements.txt`, including SciPy, Joblib, and Gunicorn.

## Repository Structure

```
customer-segmentation-ML-/
├── Mall_Customers.csv           # Mall customer dataset
├── customer_segmentation.ipynb  # Exploratory analysis/model notebook
├── customer_segmentation.pkl    # Saved clustering model
├── app.py                       # Flask application and prediction route
├── index.html                   # CSV upload page
├── requirements.txt             # Python dependencies
├── static/                      # Static assets directory
└── README.md                    # Project documentation
```

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Nancyrana1/customer-segmentation-ML-.git
cd customer-segmentation-ML-
```

### 2. Create and activate a virtual environment (recommended)

```bash
python -m venv venv
```

On Windows:

```bash
venv\Scripts\activate
```

On macOS or Linux:

```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Flask application

```bash
python app.py
```

Open the local address shown in the terminal (by default, `http://127.0.0.1:5000/`) in your browser.

## Input CSV Format

The uploaded CSV must contain these exact column names:

```csv
Annual Income (k$),Spending Score (1-100)
15,39
16,81
```

The example values above are illustrative. Include the same feature columns and compatible numeric values used to train the saved model.

## Notes and Limitations

- The web app expects the uploaded CSV to include both required feature columns.
- The Flask route currently returns the prediction results as an HTML table.
- The saved model is loaded from `customer_segmentation.pkl` relative to the application's working directory.
- The current app is a project/demo implementation. It does not include authentication, persistent upload storage, or a production deployment configuration.
- Only upload CSV files you trust. The app currently performs basic file handling and should be hardened with validation, size limits, and safer error handling before public deployment.
- Pickle files should only be loaded from trusted sources.

## Learning Outcomes

This project demonstrates a basic end-to-end machine-learning workflow: working with customer data, applying clustering, saving a trained model, and connecting that model to a Flask web interface.
