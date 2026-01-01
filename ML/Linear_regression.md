# Interview Questions for Linear Regession 
1. What is linear Regression and how it's used in predictive modeling?
   > Ans- LR is a statistical based method to model the relationship between two numerical variables by fitting the linear equation to observed data. This calibrated line serve as a
**predictive model** to forcast future outcomes based on input features.
## Key components of Linear Regression 
- Dependent Variable (Y) - the variable being predicted (Output)
- Independent Variable(s) (X)- the predictor variables. (Input)
- Coefficients - Intercept (c) and slop (\(\beta \)
- Residuals/Error- the gaps b/w predicted and observed Values.
## Core Attributes of the Model
- Linearity - The relation b/w X & Y is linear.
- Independence- Each input features must be independent of each others.
- Homoscedasity- Consistent variability in residuals along the entire rangs of predictors.
- Poor Performance in the Presence of Outliers: Sensitive to outliers during model training.
## Computationals Approach-
- **Ordinary Least Squares (OLS)**: Minimizes the sum of squared differences between observed and predicted values.
- **Gradient Descent**: Iteratively adjusts coefficients to minimize a specified cost function.
