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
## Model Performance Metrics-
- Coefficient of Determination : Measures the proportion of the variance in the dependent variable that is predictable from the independent variables.
- Root Mean Squared Error (RMSE): Provides the standard deviation of the residuals, effectively measuring the average size of the error in the forecasted values. 



2. Can you explain the diffrence b/w simple linear regression and multiple linear regression?
   > Below is an **interview-ready explanation** that is **slightly detailed**, crisp, and structured—ideal for technical + ML interviews.

---

## Difference Between Simple Linear Regression and Multiple Linear Regression

**Simple Linear Regression (SLR)** is used when we want to model the relationship between **one independent variable** and **one dependent variable**.
**Multiple Linear Regression (MLR)** is an extension of SLR where the dependent variable is influenced by **two or more independent variables**.

---

### 1. Mathematical Formulation

**Simple Linear Regression**
[
y = \beta_0 + \beta_1 x + \varepsilon
]

* Models how a single feature (x) affects the target (y)
* (\beta_1) represents the change in (y) for a unit change in (x)

**Multiple Linear Regression**
[
y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \dots + \beta_n x_n + \varepsilon
]

* Each coefficient (\beta_i) measures the **independent effect** of (x_i) on (y), assuming other variables are constant

---

### 2. Conceptual Difference

* **SLR** explains the outcome using **one factor**
* **MLR** explains the outcome using **multiple contributing factors**, which is more realistic for real-world problems

Example:

* SLR: Predict house price using **only area**
* MLR: Predict house price using **area, location, number of rooms, and age of house**

---

### 3. Complexity and Interpretation

| Aspect             | Simple Linear Regression | Multiple Linear Regression |
| ------------------ | ------------------------ | -------------------------- |
| Number of features | One                      | Two or more                |
| Model complexity   | Very low                 | Moderate to high           |
| Interpretability   | Very easy                | Slightly complex           |
| Visualization      | Straight line            | Plane / hyperplane         |
| Predictive power   | Limited                  | Higher                     |

---

### 4. Practical Considerations

* **SLR** is mostly used for:

  * Understanding relationships
  * Teaching fundamentals
  * Quick exploratory analysis

* **MLR** is used for:

  * Real-world prediction tasks
  * Business and engineering problems
  * Data-driven decision making

However, MLR introduces challenges such as:

* **Multicollinearity** between features
* **Overfitting** if too many variables are used
* Need for **feature selection and regularization**

---

### 5. Assumptions (Interview Highlight)

Both models assume:

* Linear relationship between inputs and output
* Independent observations
* Constant variance of errors (homoscedasticity)
* Normally distributed residuals

Additionally, **MLR requires low multicollinearity** among predictors.

---

### 6. Interview Closing Statement

> *Simple Linear Regression models the effect of a single variable on a target, making it easy to interpret, whereas Multiple Linear Regression incorporates multiple predictors to capture complex real-world relationships with higher predictive accuracy.*


