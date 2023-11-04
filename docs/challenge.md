# First Part Software Engineer (ML & LLMs) Challenge

## Overview

The first part of the **Software Engineer (ML & LLMs)** Application Challenge. In this, you will have the transcribed model from the .ipynb notebook to the model.py file. Each function in the model.py file is documented and explains how it works. In order to run the tests a few lines were added in the file and documented.

The **Logistic Regression model was chosen** to train and predict the data. Exploring the data, the following was found:
- The data is linear and the features are not correlated. 
    - Using a statistical test, such as the linearity test by scipy, the p-value of each attribute of the top 10 was less than 0.05, then the data to train is linear.
    - Using the .corr() function of a DataFrame, almost all the values were near 0, which led to no-correlated data.
- Logistic regression works better with linear data and no-correlated features, is also relatively fast to train and deploy.

Additionally, the following bugs were fixed:
- **exploration.ipynb**: All the code for the plots needed the 'x' and 'y' attributes to be declared in order to run. So, the attributes were included in each plot.
- **model.py**: The returning object of the preprocess function had a typo, the Union object was defined with parenthesis '()' instead of brackets '[]'. 

## Problem

A jupyter notebook (`exploration.ipynb`) has been provided with the work of a Data Scientist (from now on, the DS). The DS, trained a model to predict the probability of **delay** for a flight taking off or landing at SCL airport. The model was trained with public and real data, below we provide you with the description of the dataset:

|Column|Description|
|-----|-----------|
|`Fecha-I`|Scheduled date and time of the flight.|
|`Vlo-I`|Scheduled flight number.|
|`Ori-I`|Programmed origin city code.|
|`Des-I`|Programmed destination city code.|
|`Emp-I`|Scheduled flight airline code.|
|`Fecha-O`|Date and time of flight operation.|
|`Vlo-O`|Flight operation number of the flight.|
|`Ori-O`|Operation origin city code.|
|`Des-O`|Operation destination city code.|
|`Emp-O`|Airline code of the operated flight.|
|`DIA`|Day of the month of flight operation.|
|`MES`|Number of the month of operation of the flight.|
|`AÑO`|Year of flight operation.|
|`DIANOM`|Day of the week of flight operation.|
|`TIPOVUELO`|Type of flight, I =International, N =National.|
|`OPERA`|Name of the airline that operates.|
|`SIGLAORI`|Name city of origin.|
|`SIGLADES`|Destination city name.|

In addition, the DS considered relevant the creation of the following columns:

|Column|Description|
|-----|-----------|
|`high_season`|1 if `Date-I` is between Dec-15 and Mar-3, or Jul-15 and Jul-31, or Sep-11 and Sep-30, 0 otherwise.|
|`min_diff`|difference in minutes between `Date-O` and `Date-I`|
|`period_day`|morning (between 5:00 and 11:59), afternoon (between 12:00 and 18:59) and night (between 19:00 and 4:59), based on `Date-I`.|
|`delay`|1 if `min_diff` > 15, 0 if not.|

## Challenge

### Context:

We need to operationalize the data science work for the airport team. For this, we have decided to enable an `API` in which they can consult the delay prediction of a flight.

*We recommend reading the entire challenge (all its parts) before you start developing.*

### Part I

In order to operationalize the model, transcribe the `.ipynb` file into the `model.py` file:

- If you find any bug, fix it.
- The DS proposed a few models in the end. Choose the best model at your discretion, argue why. **It is not necessary to make improvements to the model.**
- Apply all the good programming practices that you consider necessary in this item.
- The model should pass the tests by running `make model-test`.

> **Note:**
> - **You cannot** remove or change the name or arguments of **provided** methods.
> - **You can** change/complete the implementation of the provided methods.
> - **You can** create the extra classes and methods you deem necessary.
