# Used Car Price Predictor

## Overview
This is an end-to-end regression project predicting used car prices from listing features. 
It is as a learning project, developed while working through Hands-On Machine Learning (Géron) and Pattern Recognition and Machine Learning (Bishop).
The project uses the [Vehicle Dataset from Cardekho](https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho).

## Project Structure
The project consists of two main folders:

`./notebooks/`: contains two Jupyter notebooks:
1. modelling.ipynb => main notebook, fetches data, trains and tests various ML models.
2. exploratoryDataAnalysis.ipynb => secondary notebook used for early-stage, exploratory data analysis of the training set.

`./data/`: folder where the intermediate/processed datasets are stored.

## Setup and Usage
Dependencies needed to run the notebooks are listed in `environment.yml`.
To create an environment that includes these dependencies, use:
 ```conda env create -f environment.yml```
 
 The notebook `modelling.ipynb` downloads the data from Kaggle using the Kaggle API. For this to work, 
 you will need to create a Kaggle account and configure an API token on your machine. See 
 [Kaggle API setup](https://www.kaggle.com/docs/api) for instructions.
 
 Run this notebook first to produce the training dataset used by `exploratoryDataAnalysis.ipynb`

## Results
The notebook `modelling.ipynb` trains a number of ML models on the regression task of predicting used car prices from listing features. Of the models explored,
the best-performing ones are a Linear Regression model with polynomial (degree 2) basis functions, and a Random Forest regressor. Their RMSE on the test 
dataset is:
- Linear Regression: 1252628
- Random Forest Regressor: 713933
  
The Random Forest Regressor is by far the best model trained in these notebooks, but its performance is still quite poor for the task. For reference,
the selling price is expressed in Indian Rupees, and it has (approximate) mean 1723303 and standard deviation 2461002 across the training dataset.

## TODO
- Experiment with target normalisation to improve numerical stability.
- Feature selection based on Random Forest feature importances.
- Hyperparameter tuning to address overfitting in the Random Forest model.
- Explore additional model types.
