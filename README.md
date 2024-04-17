# R in the Data World


## Table of Contents

* [Data Sourcing](#data-sourcing)
* [Data Presentation](#data-presentation)
* [Exploratory Analysis](#exploratory-analysis)
* [Data Analysis](#data-analysis)
* [Insights](#insights)
* [Recommendations](#recommendations)

- - - -

### Data Sourcing

* Dataset from KAGGLE Survey 2021


- The 2021 Kaggle DS & ML Survey received 25,973 usable responses from participants in 171 different countries and territories.
  
- The survey was live from 09/01/2021 to 10/04/2021. Respondents were allowed to complete the survey at any time during that window
   
- An invitation to participate in the survey was sent to the entire Kaggle community (anyone opted-in to the Kaggle Email List).
   The survey was also promoted on the Kaggle website (via both banners and popups) as well as on the Kaggle Twitter channel.

Please see [Kaggle Dataset](https://www.kaggle.com/c/kaggle-survey-2021/data)

- - - -

### Data Presentation

* The data are collected from 102 male and 100 female athletes.\
They consist of 13 variables.\
<br>The first two variables are categorical and especially are the gender of the 2 athlete and their sport.<br /> 
The remaining 11 variables are various measurements made on the athletes. \
The dataset is available in the file sport.txt.

* **Dataset characteristics**
<br>The Dataset has the following fields: <br /> 
**Sex**: a factor with levels {male, female}\
**Sport**: a factor with levels {BBall, Field, Gym, Netball, Row, Swim, T400m, TSprnt, WPolo }\
**RCC**: red blood cell count, in 10^{10} per liter\
**WCC**: white blood cell count, in 10^{10} per liter\
**Hc**: hematocrit, percent\
**Hg**: hemaglobin concentration, in g per decaliter\
**Ferr**: plasma ferritins, ngr per decaliter\
**BMI**: Body mass index, 102kg/cm2\
**SSF**: sum of skin folds\
**X.Bfat**: percent Body fat\
**LBM**: lean body mass, kg\
**Ht**: height, cm\
**Wt**: weight, kg

- - - -

### Exploratory Analysis

   [Exploratory Analysis](/ExploratoryAnalysis.md)
   
----

### Data Analysis

1. [Linear Regression Weight and Height](/WeightHeightLinearRegression.md)
2. [Ferretin Multiple Linear Regression](/FerretinLR.md)
3. [Ferretin Linear Regression with Log Transformed Data](/FerretinLogLR.md)
4. [Poisson log-linear model for white blood cell count](/GLMforWCC.md)
5. [Proportion of white blood cells with Binomial Log Regression](/BinomialForWCC.md)
6. [Classification for sport and sex](/ClassificationSportSex.md)

----
### Insights

- **Weight and Height Relationship**
  
The interpretation indicates that Height has a significant effect on Weight, with each additional centimeter of Height increasing Weight by 0.42 kilograms, according to the model.  
The model explains a large portion of the variability in Weight, and the predictions are expected to be accurate within approximately 11.05 kilograms, with prediction intervals providing an estimate of the range within which future observations are likely to fall.

- **Ferretin as a dependent variable with Linear Regression**
  
The multiple linear regression model for predicting Ferritin levels and it does not seem to be a good model mainly due to violation of the linear regression assumptions, so we will try to use the logarith transformed data in order to improve the model and address any violations of the assumptions.

- **Log(Ferretin) as a dependent variable with Linear Regression**
  
 The log-transformed model has shown improvement in terms of diagnostics, although the normality assumption may still not be fully addressed.  
 **So the model we prefer is the log model.**  

 
 - **White blood cell count (WCC) as a dependent variable with Poisson log-linear model**

  The Poisson model fits well the data. As the model is not overdispersed.  
  Using the final model, we can make predictions for specific scenarios for the white cells of each person.  
  


 - **Fitting a binomial logistic regression model to predict the proportion of white blood cells**
  
  The factors that are associated with changes in the proportion of white blood cells are X.Bfat and Ht, it suggests that higher body fat levels are associated with an increase in the proportion of white blood cells.

  Using the final model, we can make predictions for specific scenarios, such as predicting the expected amount of white blood cells for a female athlete involved in Gym activities.


 - **Classification**
  
  The high accuracy rates of the k-nn model and the decision tree model for predicting sex suggest that the features used in the analysis (e.g., LBM, X.Bfat) are informative for distinguishing between male and female athletes. These features may be important indicators of gender differences in athletic characteristics.
  The LDA model achieved a correct classification rate of 63.8% for predicting sports based on the provided features. While the performance is moderate, it suggests that the model can capture some patterns in the data.

----

### Recommendations

-  Consider evaluating additional factors that may influence weight, such as gender, or body composition, for a more comprehensive model.

- Consider whether additional non-linear transformations or alternative functional forms for predictors could better capture the relationship with Ferritin levels. Polynomial terms or other non-linear transformations may help address non-normality and improve model fit.

-  Finally explore opportunities for further investigation, model refinement to improve predictive performance and robustness.
