### Project Summary: Marketing ROI Analysis with Multiple Linear Regression

This project aimed to analyze a marketing dataset to understand the relationship between advertising spend on various channels (TV, Radio, Social Media) and Sales, ultimately providing an ROI-based recommendation for marketing budget allocation. A Multiple Linear Regression model was implemented using Python and `statsmodels`.

**1. Data Loading and Cleaning:**
*   The `marketing_and_sales_data_evaluate_lr.csv` dataset was loaded.
*   Initial data exploration revealed missing values across all marketing channels and Sales. These missing values were handled by dropping the corresponding rows from the dataset, ensuring a complete and robust dataset for analysis.

**2. Exploratory Data Analysis (EDA) and Variable Selection:**
*   A correlation analysis was performed to identify the marketing channel most strongly correlated with Sales.
*   **Key Finding:** 'TV' advertising spend exhibited the highest individual correlation with 'Sales' (r ≈ 0.999). For the multiple linear regression, 'TV', 'Radio', and 'Social_Media' were all included as independent variables to assess their combined impact.
*   A scatter plot visualizing 'TV' spend vs. 'Sales' further reinforced this strong linear trend.
*   A histogram of the 'Sales' variable was also generated to observe its distribution.

**3. Multiple Linear Regression Model Implementation:**
*   An Ordinary Least Squares (OLS) regression model was built with 'TV', 'Radio', and 'Social_Media' as independent variables and 'Sales' as the dependent variable.
*   **Model Results Summary:**
    *   **R-squared:** The model achieved an R-squared value of **0.999**, indicating that approximately 99.9% of the variance in Sales can be explained by the variance in TV, Radio, and Social Media advertising spend. This suggests an excellent fit of the model to the data.
    *   **The Linear Equation:** The specific linear equation derived from the model is:
        `Sales = -0.1340 + 3.5626 * TV - 0.0040 * Radio + 0.0050 * Social_Media`
    *   **Coefficients and P-values:**
        *   **Intercept (const):** Coefficient = -0.1340, P-value = 0.193. Not statistically significant at standard alpha levels.
        *   **TV Coefficient:** Coefficient = 3.5626, P-value = 0.000. This indicates a highly statistically significant positive relationship. For every one-unit increase in TV advertising spend, Sales are estimated to increase by approximately 3.56 units, holding other factors constant.
        *   **Radio Coefficient:** Coefficient = -0.0040, P-value = 0.685. Not statistically significant. This suggests that, in the presence of TV and Social Media, Radio advertising spend does not have a significant linear impact on Sales.
        *   **Social Media Coefficient:** Coefficient = 0.0050, P-value = 0.842. Not statistically significant. Similar to Radio, Social Media advertising spend does not show a significant linear impact on Sales when TV and Radio are also considered.

**4. Assumption Checking:**
*   Diagnostic plots were generated to verify the key assumptions of linear regression:
    *   **Residuals vs Fitted Plot:** This plot showed a random scatter of residuals around zero, suggesting linearity and homoscedasticity (constant variance of residuals).
    *   **Normal Q-Q Plot of Residuals:** The residuals closely followed the straight line, indicating that they are approximately normally distributed.
    *   **Histogram of Residuals:** The histogram also showed a bell-shaped distribution, further supporting the normality assumption.

**5. Conclusion and Business Recommendation:**
*   The analysis confirms a highly significant and strong positive relationship between marketing spend across the channels and Sales, primarily driven by TV advertising. The model demonstrates excellent explanatory power.
*   **Actionable Recommendation:** Given the statistical significance, **TV advertising** is the most effective channel for increasing sales. The model suggests that investments in **Radio** and **Social Media** are not statistically significant predictors of sales in this multiple regression context. Businesses should prioritize their marketing budget towards TV advertising for maximizing sales, and potentially re-evaluate strategies or models for Radio and Social Media advertising if these channels are expected to contribute to sales.
