COVID-19 Hospitalization Analysis Project

0) Problem Statement
 
Can we predict which COVID-19 probable cases will be admitted to the hospital?
We will use a variety of classifiers to develop our models.
Success will be evaluated on our accuracy of predicting whether a person was hospitalized or not.
It will be interesting to see what factors influence the probability of hospitalization. 

1) Executive Summary
 
We gathered/collected our COVID data directly from the Center for Disease Control and Prevention website, where all available data sets are public.
We were interested in predicting whether a COVID-19 probable cases will be admitted to the hospital based on the gathered data. The data set contained over 10 million submissions of covid cases from 2019 to 2021 across the United States. 

After Data collection, we cleaned our data by removing columns with over 80% null values that would't help us in building our models. We then dropped NaNs in the remaining rows and engineered some additional features, resulting in a data frame with over 3 million rows and 70 columns. With our new clean data set, we created some visualizations and conducted proper EDA to better understand the data collected for proper model analysis in the future. We found from the visualizations that the features most highly correlated with hospitalization are people over the age of 65, residents of NY, residents of MN, etc. We also found that the features least correlated with hospitalization are people between the age of 18 - 49 and 0 - 17, as well as residents of UT. 
We also found hospitalization rates by gender, race, age group, location, and time-period.



<img src = "images/age_hospitalizations.jpg"> <img src = "images/gender_hospitalizations.jpg">

<img src = "images/state_hospitalizations.jpg"> 

We reprocessed our final COVID Data, train-test-split our X and y variables, and created models using Logistic Regression and ANN Machine Learning, for scoring and predicting hospitalization based on our selected features. We created visualizations of our modeled data and predictive variables, created a confusion matrix for analysis, analyzed coefficients, and generated a classification report as well. We found that our Logistic Regression model gave us the best score, and we were able to predict hospitalization with the highest accuracy based on our data from the CDC. Below is our final confusion matrix:

<img src = "images/final_confusion_matrix.png">

2) Table of Contents

[COVID Hospitalization Analysis](covid_hospital_final.ipynb)

[EDA for Feature Importances](EDA_feature_importances.ipynb)

[COVID Data](data/covid_cases_cleaned.csv) 

[Cleaned/Final Covid Data](data/final_df.pkl)

[Presentation](presentation/Covid-Presentation.pdf)

[Images](images/)
 
3) Data and Data Dictionary

DESCRIPTIVE ABSTRACT: Data set contains public information from the CDC.

SOURCES: https://data.cdc.gov

|Feature|Type|Data set|Description|
|---|---|---|---|
|**case_month**|*object*|final_df|The month in which the case was reported in. (i.e. 2021-01)
|**res_state**|*object*|final_df|The state in which the case was reported in. (i.e. NJ) 
|**age_group**|*object*|final_df|The age group of the person with the reported case (i.e. 0 - 17 years)
|**sex**|*object*|final_df|The gender of the individual reported case. (Male / Female)
|**race**|*object*|final_df|The race of the individual reported case. (i.e. American Indian/Alaskan Native)
|**ethnicity**|*object*|final_df|The ethnicity of the individual reported case. (i.e. Hispanic/Latino)
|**case_onset_interval**|*float*|final_df|The length of time between the reported case and COVID symptoms. (i.e. 1.0 = 1 Day)
|**current_status**|*object*|final_df|The current status of the COVID case. (i.e. Confirmed Ovid Case) 
|**symptom_status**|*object*|final_df|The current symptom status of the COVID case. (i.e. Symptomatic)
|**hosp_yn**|*object*|subreddit_df|The hospitalization status of the COVID case. (i.e. yes)
|**death_yn**|*object*|subreddit_df|The death status of the COVID case. (i.e. no)

4) Conclusions and Recommendation

We can accurately predict whether a probable COVID case will be admitted to the hospital with an accuracy of ~93.2%.
It was difficult to create an accurate prediction that would perform better than our baseline accuracy of ~92.6%.
Through the process of cleaning our data and exploring different predictive modeling techniques, we did slightly better than our baseline, but also had interesting findings.

We notice all the different correlative features that contribute the most to hospitalization: age group, location, and race. 
If conducting a similar project, I would recommend gathering even more data from the CDC across a larger span of time that COVID has been present. Also, there are many states that are under-reporting COVID data for unspecified reasons, this can cause inaccuracy in our analysis. Data sets with less Null values would fair better. 

5) Areas for Further Research/Study

It would be interesting to see what results a similar analysis would bring a year from now in 2022, as we are entering the final stages of the pandemic.

It would also be interesting to bring in more features that weren't available in this data set that may have a large impact on COVID hospitalization.