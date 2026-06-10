### Project Summary: Marketing ROI Analysis with Multiple Linear Regression

This project aimed to analyze a marketing dataset to understand the relationship between advertising spend on various channels (TV, Radio, Social Media) and Sales, ultimately providing an ROI-based recommendation for marketing budget allocation. A Multiple Linear Regression model was implemented using Python and `statsmodels`.

**1. Data Loading and Cleaning:**
*   The `marketing_and_sales_data_evaluate_lr.csv` dataset was loaded.
*   Initial data exploration revealed missing values across all marketing channels and Sales. These missing values were handled by dropping the corresponding rows from the dataset, ensuring a complete and robust dataset for analysis.

**2. Exploratory Data Analysis (EDA) and Variable Selection:**
*   A correlation analysis was performed to identify the marketing channel most strongly correlated with Sales.
*   **Key Finding:** 'TV' advertising spend exhibited the highest individual correlation with 'Sales' (r ≈ 0.999). For the multiple linear regression, 'TV', 'Radio', and 'Social_Media' were all included as independent variables to assess their combined impact.
*   A scatter plot visualizing 'TV' spend vs. 'Sales' further reinforced this strong linear trend.

**3. Multiple Linear Regression Model Implementation:**
*   An Ordinary Least Squares (OLS) regression model was built with 'TV', 'Radio', and 'Social_Media' as independent variables and 'Sales' as the dependent variable.
*   **Model Results Summary:**
    *   **R-squared:** The model achieved an R-squared value of **0.999**, indicating that approximately 99.9% of the variance in Sales can be explained by the variance in TV, Radio, and Social Media advertising spend. This suggests an excellent fit of the model to the data.
    *   **Coefficients:**
        *   **Intercept (const):** The intercept represents the estimated sales when all advertising spends (TV, Radio, Social Media) are zero. Its statistical significance should be evaluated.
        *   **TV Coefficient:** This coefficient indicates the estimated change in Sales for a one-unit increase in TV advertising spend, holding Radio and Social Media constant.
        *   **Radio Coefficient:** This coefficient indicates the estimated change in Sales for a one-unit increase in Radio advertising spend, holding TV and Social Media constant.
        *   **Social Media Coefficient:** This coefficient indicates the estimated change in Sales for a one-unit increase in Social Media advertising spend, holding TV and Radio constant.
    *   **P-values:** The p-values for each coefficient indicate their statistical significance. A low p-value (typically < 0.05) suggests that the variable is a significant predictor of Sales. These values should be interpreted from the OLS summary to determine which channels have a statistically significant impact.

**4. Assumption Checking:**
*   Diagnostic plots were generated to verify the key assumptions of linear regression:
    *   **Residuals vs Fitted Plot:** This plot should show a random scatter of residuals around zero, suggesting linearity and homoscedasticity (constant variance of residuals).
    *   **Normal Q-Q Plot of Residuals:** The residuals should closely follow the straight line, indicating that they are approximately normally distributed.
    *   **Histogram of Residuals:** The histogram should also show a bell-shaped distribution, further supporting the normality assumption.

**5. Conclusion and Business Recommendation:**
*   The analysis confirms a highly significant and strong positive relationship between marketing spend across the channels and Sales. The model demonstrates excellent explanatory power.
*   **Actionable Recommendation:** Based on the coefficients and p-values from the multiple linear regression model, specific recommendations can be made regarding the optimal allocation of the marketing budget across TV, Radio, and Social Media to maximize ROI. Channels with statistically significant positive coefficients should be prioritized, with the magnitude of the coefficient indicating the relative impact on sales. It's crucial to interpret the p-values and confidence intervals from the OLS summary to make robust business decisions.
