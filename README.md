# Airbnb NYC Analysis

## Overview:
* Analyzed over 50,000 NYC Airbnb entries using NumPy and Pandas and discovered that Manhattan has ~80% of the market share, comparison models visualized with Matplotlib and Seaborn.
* Employed 5 different regression models and achieved a 99% accuracy in predicting geographic location based on pricing information, enabling actionable insights into targeting new clients and optimizing market strategies.
* Created an effective model that provides actionable insights into targeting new clients and optimizing market strategies.

## Libraries and Resources Used
**Python Version:** Python 3.9.13  
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn, plotly, and textwrap  
**Dataset:** airbnb_ny.csv (included in repository; obtained from Springboard)

## Data Cleaning/Exploratory Data Analysis
To enhance the code's overall readability and applicability to our models later, I performed the following:
*	Counted the # of listings in each borough and compared the amounts in a bar plot and the percentages in a pie graph
*	Created Revenue column and graphed the average revenue for each borough
*	Investigated for the top 3 highest revenue neighbourhoods in Manhattan, Brooklyn, & Queens
*	Made a graph that shows the distribution of room types in Manhattan, Brooklyn, & Queens. Then, identified the top performing room type in the top 3 neighbourhoods of Manhattan, Brooklyn, & Queens.

![](https://github.com/Max-Boonjindasup/airbnb_analysis/blob/main/pie_listings_by_borough.png)
![](https://github.com/Max-Boonjindasup/airbnb_analysis/blob/main/highest_revenue_room_type.png)

## Model Building

1. Removed irrelavant categorical attributes and the Revenue column as to avoid multicollinearity.
2. Replaced 0's and NaN values with attribute means.
3. Checked for possible correlations between variables via correlation matrix.
4. Transformed the categorical variables into dummy variables.
5. Standardized features
6. Splitted data into train and tests sets (test size = 30%).   

I trained 5 different models and evaluated them using an array of metrics: Mean Squared Error, Root Mean Squared Error, Mean Absolute Error, and R2. For logistic regression, precision, recall, F1-score, and accuracy were reported along with the accompanying confusion matrix

Models:
*	**Linear Regression** – Baseline model; iterated on different predictor variables (ie number_of_reviews, latitude, etc.)
*	**Polynomial Regression** – Having 6 attributes, I wanted a model to use all my attributes when predicting price
*	**Multinomial Logistic Regression** – In this case, I flipped the question and made a classification model where we predict borough from price.
*	**Decision Tree Regression** – Testing both questions (borough predicts price vs price predicts borough) with another model
*	**Random Forest Regression** – Again, testing both questions (borough predicts price vs price predicts borough) with another model

## Model performance
Most models were trained to predict pricing based on a variety of attributes, but changing to predicting borough (Queens, Brooklyn, Staten Island, Manhattan, and Bronx) based off price produced excellent scores.
The Logistic Regression model far outperformed the other approaches on the test sets.
*	**Linear** : RMSE = 0.825
*	**Polynomial**: RMSE = 0.773
*	**Logistic**: RMSE = 0.224 (ACC = 0.986)
*	**Decision Tree**: RMSE = 0.822
*	**Random Forest**: RMSE = 0.822

![](https://github.com/Max-Boonjindasup/airbnb_analysis/blob/main/confusion_matrix_airbnb_attributes.png)
![](https://github.com/Max-Boonjindasup/airbnb_analysis/blob/main/logistic_reg_score.png)
