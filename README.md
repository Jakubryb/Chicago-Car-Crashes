# Phase-3

![Chicago Car Crash Cover](./Images/Chicago_Car_Crash_Cover.PNG)


# Chicago Car Crashes

**Authors**: [Noble Tang](mailto:NobleTang@gmail.com), 
            [Jakub Rybicki](mailto:jakubry92b@gmail.com), and 
            [Lenore Perconti](mailto:Lenorephotography@gmail.com)
 
## Overview

In this project we looked at traffic incident data from the City of Chicago. We joined two data sets, processed them, and used modeling to infer information on traffic incidents at night.

## Business Understanding

Our stakeholder is City of Chicago Department of Transportation. They are interested in learning more about what factors contribute to severe traffic incidents for drivers at night.

Severe traffic incidents we defined as FATAL or INCAPACITATING from the INJURY_TYPE column.

Night we defined as the hours between 10pm to 5 am, or hours 22 through 5 in the CRASH_HOUR column.

## Data Understanding

The data used was sourced from the following websites:

https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if

https://data.cityofchicago.org/Transportation/Traffic-Crashes-People/u6pd-qa9d

The data was downloaded on Friday, October 22. Attempts to reproduce this notebook may result in inconcistancies since the online source is updated weekly.

These datasets are include very recent data and information from 2013 to present. The number of variables and columns in this dataset made it challenging to clean and use, however the broad scope of the data makes it a good candidate for exploring the business problem at hand.

## Data Preperation

For data preparation, we formatted many columns. We later decided we didn't need to use many of them. We filled in missing data with appropriate values which is further discussed in the notebook.

The size of the original datasets were too large to upload to github, we create a cleaned and merged dataset saved as clean_data.csv.

## Modeling

For all our models we built a pipeline that accomplished the following:

Column Transformers, One Hot Encoded categorical columns
Used SMOTE strategy to synthesize new examples for the minority class and address class imbalance
Perform a grid search to find optimal

#### Baseline Model

A baseline model helps us find the features we are most interested in and where we can focus modeling iterations on to get better models.

SMOTE logistic regression with just traffic control device (picked from our decision tree). This is the simplest model to give us a place to start.

## Discussion and Conclusions

In conclusion, our best classification model was done with K_Nearest_Neighbors run with selected key features resulting in an accuracy score of 87%. These features were DEVICE_CONDITION, WEATHER_CONDITION, LIGHTING_CONDITION, ROADWAY_SURFACE_COND, CRASH_DAY_OF_WEEK.
Due to the imbalanced classification found within our target variable as well as in our slected features we had implemented the SMOTE technique of oversampling and undersampling within our test splits. We also used a pipeline and GridSearchCV to select our optimal hyperparameters within this model which resulted in this model outperforming the decision tree and logistic regression models.
The complexity of this dataset did make implimenting a succesful model a challenge. Further research would involve more time and care spent on EDA and transofrming the data.


## Future Research

Further research we suggest to include budgetary and resource restrictions that the DOT must consider when implementing solutions.

## For More Information

See the full analysis: [Jupyter Notebook](./Final Notebook.ipynb), [Jupyter Notebook PDF](./Final Notebook.pdf) or review this 
[Presentation](https://docs.google.com/presentation/d/1WZkj35Cn_xHzUtpLqt1yHE4x3BEcWc0jfyTcZTvkTf8/edit?usp=sharing).

## Repository Structure

```
├── Images
├── data
├── Appendix
├── .gitignore
├── README.md
├── Final Notebook.ipynb
├── Phase 3 - CHICAGO CAR CRASHES.pptx
└── clean_data.csv
