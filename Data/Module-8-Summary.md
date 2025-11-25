# Chapter 6 – Preparing to Model the Data 

## 1. Supervised vs. Unsupervised Methods
- **Supervised:** target variable exists; model learns mapping from predictors to target.  
  *Examples:* 
	 > 1. regression, -> *see Chapter 5*
	 > 2. decision trees,
	 > 3. neural networks,
	 > 4. k-NN.
- **Unsupervised:** no target variable.  
  *Examples:*
	> 1. clustering -> *uncover voter profiles based on income, gender, etc.*
	> 2. association mining

[^1]
## 2. Statistical vs. Data Mining Methods

Statistical methods differ in 2 ways:
1. Statistical inference with huge sample size will prob result in statistical significance. *does not mean the result has practical significance*
2. There is a big difference between statistical methodology and pure Data mining:
- Statistical inference often assumes an **a priori hypothesis**.  
- Data mining does **not have a priori hypothesis** , is more exploratory and can easily produce **spurious/phantom patterns** due to large sample sizes.

## 3. Cross-Validation
Purpose: avoid spurious patterns and ensure **generalizability**.

### Twofold CV:
1. Randomly split data into **training** and **test** sets.  
2. Train on training set, hide test-set target, predict, compare to true values.  
3. Validate that training/test sets are similar

|Type of Target     | Test    |
| --- | --- |
|Continuous|  Two-Sample t-test for difference in means   |
|Flag|     Two-Sample Z test for difference in proportions |
|Multinominal| Test for homogeneity of proportions|


### k-Fold CV:
- Partition data into **k** folds (*subsets*).  
- Train on k–1 folds, test on the remaining one.  
- Repeat k times; combine results via averaging/voting.  
- Standard: **k = 10**.

| benefit | drawback |
| --- | --- |
| each record appears exactly once | requisite validation more difficult |

**Three-step summary:**
1. Partition and validate  
2. Build model
3. Evaluate on test set

## 4. Overfitting and Underfitting
- **Overfitting:** model is too complex, memorizes noise; good training accuracy but poor test accuracy.  
- **Underfitting:** model too simple; high error for both sets.  
- Optimal point = **minimum test-set error** (see Figure 6.1).

![Figure6.1](images/data/Figure_6.1.png)

## 5. Bias–Variance Trade-off
[^2]
- Low-complexity models: **high bias, low variance**.  
- High-complexity models: **low bias, high variance**.  
- Goal: balance the two.  
- MSE combines both: $MSE = variance + bias²$

| Model Type            | Bias | Variance | Behavior                                     |
|-----------------------|------|----------|-----------------------------------------------|
| **Low-complexity**    | High | Low       | Underfits (too simple, systematic errors)     |
| **High-complexity**   | Low  | High      | Overfits (too specific, unstable predictions) |

## 6. Balancing the Training Data (for classification with rare classes)
- Use when one class is very rare (fraud, churn, etc.).  
- Otherwise, the model may predict only the majority class.

### Two balancing methods:
1. **Resampling rare class** (oversampling with replacement).  
2. **Setting aside majority-class records** (downsampling).

  Formula for number of added/reduced samples:
$$
   x = \frac{p \cdot records - rare}{1 - p}
   $$
$\text{where:}$
$x = \text{is the required number of resampled records}$
$p = \text{is the desired proportion of rare values in the balaced data}$
$\text{records} = \text{represents numer of records in the unbalanced data}$
$\text{rare} = \text{represents the current number of rare target values}$




### Important rule:
- **Never balance the test set**, because real-world data is unbalanced.

## 7. Establishing Baseline Performance
- Needed to judge whether a model is “good”.

### Examples:
- For churn: overall churn rate is the baseline.  
- Compare absolute vs. relative improvements (e.g., drop from 14.49% to 9.99%).  
- For regression: compare to the naïve **mean model** (ŷ-model).  
- Model must outperform the baseline; otherwise something is wrong.

[^1]: Unsupervised methods don`t mean that they need no human involvement.

[^2]: *Bias: Systematic error caused by an overly simple model that cannot capture the true underlying pattern.*  
	*Variance: Instability caused by an overly complex model that changes strongly with small fluctuations in the training data.*
