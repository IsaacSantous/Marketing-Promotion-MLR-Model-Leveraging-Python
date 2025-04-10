#### Marketing-Promotion-MLR-Model-Leveraging-Python

#### Introduction
Multiple linear regression helps data professionals estimate the linear relationship between one continuous dependent variable and two or more independent variables. This is a useful skill because it enables you to compare more than one variable against the variable you're measuring. This provides the opportunity for much more thorough and flexible analysis.

In this project, I will analyse a small business's historical marketing promotion data. Each row corresponds to an independent marketing promotion where the business uses TV, social media, radio, and influencer promotions to increase sales. The stakeholders are interested in finding variables that predict sales to help them target their marketing efforts. To address the business request, I will conduct a multiple linear regression analysis to estimate sales from a combination of independent variables. This will include:
•	Exploring and cleaning data
•	Using plots and descriptive statistics to select the independent variables
•	Creating a fitting multiple linear regression model
•	Checking model assumptions
•	Interpreting model outputs and communicating the results to non-technical stakeholders

#### Step 1: Import packages and load dataset
#### Step 2: Exploratory Data Analysis
The features in the data are:
•	TV promotional budget (in "Low," "Medium," and "High" categories)
•	Social media promotional budget (in millions of dollars)
•	Radio promotional budget (in millions of dollars)
•	Sales (in millions of dollars)
•	Influencer size (in "Mega," "Macro," "Micro," and "Nano" categories)

Create a pairplot to visualize the relationship between the continuous variables in the dataset.
From the pairplot, Radio and Social Media both appear to have linear relationships with Sales. Given this, Radio and Social Media may be useful as independent variables in a multiple linear regression model estimating Sales. TV and Influencer are excluded from the pairplot because they are not numeric. 

Calculate the mean sales for each categorical variable
There are two categorical variables: TV and Influencer. To characterize the relationship between the categorical variables and Sales, find the mean Sales for each category in TV and the mean Sales for each category in Influencer. From the calculated mean sales for each categorical variable, the average Sales for High TV promotions is considerably higher than for Medium and Low TV promotions. Hence, TV may be a strong predictor of Sales. The categories for Influencer have different average Sales, but the variation is not substantial. Hence, Influencer may be a weak predictor of Sales.

#### Step 3: Model Building
	Fit a multiple linear regression model that predicts sales
	Check model assumptions: Check that all five multiple linear regression assumptions are upheld for the model.

#### Step 4: Results and evaluation
Using TV and Radio as the independent variables results in a multiple linear regression model with R2=0.904. In other words, the model explains 90.4% of the variation in Sales. This makes the model an excellent predictor of Sales. When TV and Radio are used to predict Sales, the model coefficients are:

 ![image](https://github.com/user-attachments/assets/3691d879-5080-4e8e-a60e-b02017529541)
![image](https://github.com/user-attachments/assets/13de646c-00e5-4d8a-a5aa-6dd8d8f42f30)
 
The default TV category for the model is High since there are coefficients for the other two TV categories, Medium and Low. Because the coefficients for the Medium and Low TV categories are negative, that means the average of sales is lower for Medium or Low TV categories compared to the High TV category when Radio is at the same level.

For example, the model predicts that a Low TV promotion is 152.0897 lower on average compared to a high TV promotion given the same Radio promotion.
The coefficient for Radio is positive, confirming the positive linear relationship shown earlier during the exploratory data analysis.
The p-value for all coefficients is 0.000, meaning all coefficients are statistically significant at p=0.05. The 95% confidence intervals for each coefficient should be reported when presenting results to stakeholders. For example, there is a 95% chance that the interval [−162.225,−141.954] contains the true parameter of the slope of βTVLow, which is the estimated difference in promotion sales when a Low TV promotion is chosen instead of a High TV promotion.

#### Summary
According to the model, high TV promotional budgets result in significantly more sales than medium and low TV promotional budgets.
High TV promotional budgets have a substantial positive influence on sales. The model estimates that switching from a high to medium TV promotional budget reduces sales by $73.4835 million (95% CI [−80.530,−66.437]), and switching from a high to low TV promotional budget reduces sales by $152.0897 million (95% CI [−162.225,−141.954]). The model also estimates that an increase of $1 million in the radio promotional budget will yield a $2.8864 million increase in sales (95% CI [2.460,3.312]).

#### Recommendation
Thus, it is recommended that the business allot a high promotional budget to TV when possible and invest in radio promotions to increase sales.

