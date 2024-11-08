# BTP

## Overview

This repository contains the files and code used in my B.Tech project focused on analyzing and modeling ignition time data using machine learning techniques.

## Contents

- `BTP_code.ipynb`: Jupyter Notebook containing the data processing, model training, and evaluation.
- `README.md`: This documentation file.

## Project Description

The project involves the following key steps:

1. **Data Uploading and Importing:** Uploading the dataset to Google Colab and importing necessary libraries.
2. **Data Cleaning:**
   - Removing unnecessary columns.
   - Handling missing values.
   - Renaming columns for clarity.
   - Filtering out specific data points.
3. **Data Analysis:** Exploring the dataset to understand its structure and characteristics.
4. **Modeling Approach:**
   - Utilizing TensorFlow and Keras for building neural network models.
   - Implementing multiple activation functions, BatchNormalization, Dropout layers, and weight decay with the Adam optimizer.
   - Training models with various configurations to evaluate performance.
5. **Results Visualization:** Plotting actual vs. predicted ignition times and analyzing model performance metrics.

## Results so far
As of now, we have the following results:
| x   | activation  | optimizer | MSE       | RMSE      | val_loss  |
|-----|-------------|-----------|-----------|-----------|-----------|
| 0.2 | relu        | Adam      | 0.719666  | 0.848331  | 1.078066  |
| 0.2 | leaky_relu  | Adam      | 0.674110  | 0.821042  | 1.400572  |
| 0.2 | elu         | Adam      | 0.794307  | 0.891239  | 9.928001  |
| 0.2 | selu        | Adam      | 13.445637 | 3.666829  | 25.986280 |
| 0.2 | softplus    | Adam      | 0.236492  | 0.486305  | 1.287166  |
| 0.2 | swish       | Adam      | 3.993275  | 1.998318  | 4.561851  |
| 0.2 | gelu        | Adam      | 0.208417  | 0.456527  | 0.215580  |
| 0.4 | relu        | Adam      | 11.210703 | 3.348239  | 51.368652 |
| 0.4 | leaky_relu  | Adam      | 37.886464 | 6.155198  | 37.544548 |
| 0.4 | elu         | Adam      | 0.482459  | 0.694593  | 0.370725  |
| 0.4 | selu        | Adam      | 35.482405 | 5.956711  | 64.333427 |
| 0.4 | softplus    | Adam      | 11.033994 | 3.321746  | 16.743786 |
| 0.4 | swish       | Adam      | 8.186021  | 2.861122  | 9.589518  |
| 0.4 | gelu        | Adam      | 11.592155 | 3.404725  | 37.012112 |
| 0.6 | relu        | Adam      | 2.159671  | 1.469582  | 5.052184  |
| 0.6 | leaky_relu  | Adam      | 39.440372 | 6.280157  | 69.183243 |
| 0.6 | elu         | Adam      | 0.653649  | 0.808486  | 1.041007  |
| 0.6 | selu        | Adam      | 2.924356  | 1.710075  | 23.646164 |
| 0.6 | softplus    | Adam      | 0.749792  | 0.865905  | 2.239024  |
| 0.6 | swish       | Adam      | 14.506614 | 3.808755  | 17.348431 |
| 0.6 | gelu        | Adam      | 1.165280  | 1.079481  | 3.665920  |
| 0.8 | relu        | Adam      | 4.007132  | 2.001782  | 4.175528  |
| 0.8 | leaky_relu  | Adam      | 47.939118 | 6.923808  | 55.334492 |
| 0.8 | elu         | Adam      | 12.590790 | 3.548350  | 27.574987 |
| 0.8 | selu        | Adam      | 0.311026  | 0.557697  | 3.995277  |
| 0.8 | softplus    | Adam      | 2.265964  | 1.505312  | 4.038035  |
| 0.8 | swish       | Adam      | 13.475024 | 3.670834  | 16.272375 |
| 0.8 | gelu        | Adam      | 11.296475 | 3.361023  | 12.859424 |


## Dependencies

Ensure you have the following libraries installed:

- pandas
- numpy
- tensorflow
- matplotlib
- scikit-learn

You can install them using:

```bash
pip install pandas numpy tensorflow matplotlib scikit-learn