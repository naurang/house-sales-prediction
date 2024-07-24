# house-sales-prediction

---

# House Sales in King County, USA

This dataset contains house sale prices for King County, which includes Seattle. It includes homes sold between May 2014 and May 2015.

## Dataset Description

The dataset provides various attributes related to the houses sold. Below is the description of the variables included:

| Variable        | Description                                           |
| --------------- | ----------------------------------------------------- |
| `id`            | A notation for a house                                |
| `date`          | Date house was sold                                   |
| `price`         | Price is prediction target                            |
| `bedrooms`      | Number of bedrooms                                    |
| `bathrooms`     | Number of bathrooms                                   |
| `sqft_living`   | Square footage of the home                            |
| `sqft_lot`      | Square footage of the lot                             |
| `floors`        | Total floors (levels) in house                        |
| `waterfront`    | House which has a view to a waterfront                |
| `view`          | Has been viewed                                       |
| `condition`     | How good the condition is overall                     |
| `grade`         | Overall grade given to the housing unit, based on King County grading system |
| `sqft_above`    | Square footage of house apart from basement           |
| `sqft_basement` | Square footage of the basement                        |
| `yr_built`      | Year built                                            |
| `yr_renovated`  | Year when house was renovated                         |
| `zipcode`       | Zip code                                              |
| `lat`           | Latitude coordinate                                   |
| `long`          | Longitude coordinate                                  |
| `sqft_living15` | Living room area in 2015 (implies some renovations)   |
| `sqft_lot15`    | Lot size area in 2015 (implies some renovations)      |

## Setup Instructions

To run this project locally, you will need to install the required libraries. If you are using Anaconda, you can install the necessary libraries by uncommenting the following lines in your environment setup script:

```bash
# All Libraries required for this lab are listed below. 
# !mamba install -qy pandas==1.3.4 numpy==1.21.4 seaborn==0.9.0 matplotlib==3.5.0 scikit-learn==0.20.1
```

If your environment doesn't support `!mamba install`, use `!pip install` instead.

### Suppress Warnings

To suppress warnings, you can use the following code:

```python
import warnings

def warn(*args, **kwargs):
    pass

warnings.warn = warn
```

### Required Libraries

Ensure you have the following libraries installed:

```python
import piplite
await piplite.install(['pandas','matplotlib','scikit-learn','seaborn', 'numpy'])

import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler, PolynomialFeatures
from sklearn.linear_model import LinearRegression
%matplotlib inline
```

## Data Import

You can download the dataset using the following functions if you are running the lab locally:

```python
from pyodide.http import pyfetch

async def download(url, filename):
    response = await pyfetch(url)
    if response.status == 200:
        with open(filename, "wb") as f:
            f.write(await response.bytes())

file_name = 'https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DA0101EN-SkillsNetwork/labs/FinalModule_Coursera/data/kc_house_data_NaN.csv'

await download(file_name, "kc_house_data_NaN.csv")
file_name = "kc_house_data_NaN.csv"
```

Load the data using Pandas:

```python
df = pd.read_csv(file_name)
```

## Data Wrangling and Exploration

For detailed exploration and analysis of the dataset, follow the steps outlined in the Jupyter notebook provided in this repository.

## Model Development and Evaluation

The repository contains code for developing various models to predict house prices based on the provided features. The models include:

- Linear Regression
- Polynomial Regression
- Ridge Regression

Refer to the Jupyter notebook for step-by-step instructions and code implementation.

---
