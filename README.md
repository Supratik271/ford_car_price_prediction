# Ford Car Price Analysis & Prediction

This is a small data science / machine learning project where I explored a dataset of used Ford cars and built a simple model to predict their prices.

I started this as a Jupyter Notebook while learning the basics of data analysis and machine learning. The main idea was to understand the dataset first, look for patterns, and then see how well a Linear Regression model could predict car prices.

## What is in this project?

The notebook covers:

- Loading and inspecting the dataset
- Basic exploratory data analysis (EDA)
- Checking for missing values
- Looking at price distributions
- Correlation between numerical features
- Comparing prices across Ford models, fuel types, transmission types, and engine sizes
- Looking at mileage and MPG against price
- Preparing numerical and categorical features
- One-hot encoding categorical variables
- Standardizing numerical variables
- Splitting the data into training and testing sets
- Training a Linear Regression model
- Evaluating the model using MAE, RMSE, and R²
- Comparing actual and predicted prices
- Making a simple prediction from a test example

## Dataset

The dataset is stored in `ford.csv`.

It contains **17,966 rows** and **9 columns**:

| Column | Description |
| --- | --- |
| `model` | Ford car model |
| `year` | Year of the car |
| `price` | Listed car price (target) |
| `transmission` | Transmission type |
| `mileage` | Mileage |
| `fuelType` | Fuel type |
| `tax` | Vehicle tax |
| `mpg` | Miles per gallon |
| `engineSize` | Engine size |

The dataset has no missing values in these columns.

## Model result

For the current train/test split (`test_size=0.33`, `random_state=42`), the Linear Regression baseline gives approximately:

- **MAE:** 1,377.19
- **RMSE:** 1,903.11
- **R²:** 0.8402

These numbers are specific to the current notebook workflow and dataset. They should be treated as a baseline rather than as a claim that this is the best possible pricing model.

## How to run this project

This project is designed to be run in **Jupyter Notebook / JupyterLab**.

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd ford-car-price-prediction
```

### 2. Install the dependencies

You can install everything listed in `requirements.txt` with:

```bash
pip install -r requirements.txt
```

### 3. Start Jupyter

If you already have Jupyter installed:

```bash
jupyter notebook
```

or:

```bash
jupyter lab
```

### 4. Open the notebook

Open:

`kaggle_project.ipynb`

Make sure `ford.csv` is in the **same folder** as the notebook, then run the cells from top to bottom.

## Project structure

```text
ford-car-price-prediction/
│
├── README.md
├── kaggle_project.ipynb
├── ford.csv
├── requirements.txt
└── .gitignore
```

## A note about the modelling approach

I kept the model intentionally simple because this project is mainly about learning and building a complete end-to-end workflow.

The preprocessing is handled inside a scikit-learn pipeline. This means the scaler and encoder are fitted as part of the training process instead of manually fitting them on the entire dataset first. This helps avoid data leakage between the training and test sets.

Linear Regression is a useful baseline, but used-car prices are not necessarily a linear problem. A natural next step would be to try models such as Random Forest or Gradient Boosting and compare their performance.

## Possible improvements

If I continue working on this project, I would like to:

- Try stronger regression models
- Tune model hyperparameters
- Perform more detailed data cleaning and outlier investigation
- Compare several models using the same evaluation metrics
- Add cross-validation
- Explore which features have the biggest effect on predicted price
- Build a small web app where a user can enter car details and get a predicted price

## Why I made this project

This project is part of my learning journey in data science and machine learning. I wanted to move beyond just writing individual Python commands and practice putting data loading, visualization, preprocessing, modelling, and evaluation together in one project.

