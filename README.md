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