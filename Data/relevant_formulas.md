# Relevant Formulas for the ACIT-4880 final exam

## Data transformation

1. Min-max normalization:

*Purpose: Scales every value on the fixed range of numbers from 0 to 1, one of the easiest and most powerful normalization tools to compare different values and reduce effects created by different scales.*

$X* = \frac{x - x_{\min}}{x_{\max} - x_{\min}}$

2. Z-score standardization
*Purpose: values standardization method whose mean(x) is always 0 and whose standard deviation is always 1.*

$z = \frac{x - \mu}{\sigma}$

2. Interquartile Range
*Purpose: measures the middle 50% of the ascending ordered data set (50% middle values). General basis to perform outlier analyes.*

$IRQ = Q3 - Q1$

*Values at least 1.5 times below Q1 or at least 1.5 times above Q3 are considered ***extreme values***.
