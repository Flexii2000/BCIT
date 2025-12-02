# Relevant Formulas for the ACIT-4880 final exam

## Data transformation

1. Min-max normalization:

*Purpose: Scales every value on the fixed range of numbers from 0 to 1, one of the easiest and most powerful normalization tools to compare different values and reduce effects created by different scales. The smallest value is always 0, the largest always 1.*

$X* = \frac{x - x_{\min}}{x_{\max} - x_{\min}}$

2. Z-score standardization
*Purpose: values standardization method whose mean(x) is always 0 and whose standard deviation is always 1.*

$z = \frac{x - \mu}{\sigma}$

3. Interquartile Range
*Purpose: measures the middle 50% of the ascending ordered data set (50% middle values). General basis to perform outlier analyes.*

$IRQ = Q3 - Q1$

Values at least 1.5 times below Q1 or at least 1.5 times above Q3 are considered **extreme values**.

4. Decimal Scaling
*Purpose: similar to Min-Max (maximum range of values is 0 to 1) but does not guarantee that the smallest is 0 and the largest 1.

$d digits of the largest value$

$x* = \frac{x}{10^{d}}$

## Statistical Approaches

1. Confidence intervals using the mean value

$\bar{x} \pm t_{\alpha/2} \cdot \frac{s}{\sqrt{n}}$

$\bar{x} the mean$, 
$t_{\alpha/2} the t-critical value$, 
$s the sample std deviation$,
$n the sample size$

*What to do to reduce the confidence interval:*
> - decrease the critical t-value: NOT recommended since this also decreases the quality of the confidence interval test
> - decrease the standard deviation value s: ok but normally not possible. s is a statistical constant and not a value which can be easily modified
> - increase n: increasing the sample size is the recommended approach to lower the confidence interval. The larger or sample the smaller our interval (desired).

2. Simple linear regression

$\hat{y} = b + mx $

$x the predictor$,
$\hat{y} the response$
$(y - \hat{y}) the prediction error or \textbf{residual}$

3. Correlation coefficient (r value)

$r = \frac{\text{Cov}(x,y)}{\sigma_x \sigma_y}$

*Value is always between -1 and 1, -1 means perfect negative, +1 means perfect positive correlation.*

## Evaluation metrics for Regressions

1. Mean Absolute Error (MAE)

$MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|$

2. Mean Squared Error (MSE)

$MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$

3. Root Mean Square Error (RMSE)

$RMSE = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2}$

4. $R^2$ Score

$R^2 = 1 - \frac{unexplained Variance}{total Variance} = 1 - \frac{SSE}{SST}$

5. Adjusted $R^2$ Score

$\text{Adjusted } R^2 = 1 - \frac{(1 - R^2)(n - 1)}{n - p - 1}$
