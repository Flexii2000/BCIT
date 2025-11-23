# Chapter 7 — k-Nearest Neighbor (Test Summary)

## Classification Task
Classification most common data mining task:
*Examples:*
> Banking -> determine whether a mortgage application is good
> Education -> place a student into particular track with respect to special needs
> Medicine -> diagnose whether a disease is present
>  etc.

## Classification Basics
Categorical target; algorithm learns relationships between predictors and target using training set. 

|Subject | Age | Gender | Occupation | Income Bracket |
| --- | --- | ---| --- | --- |
|001|47|F| Software Engineer|High|
|002|28|M| Marketing Consultant| Middle|
|003|35|M|Unemployed| Low|
|...|...|...|...|...|

## kNN Overview
Instance-based learning: 
store training records -> classify new record by similarity to nearest neighbors.  

**Used for classification, estimation, prediction.**  


## Distance Functions
**Euclidean distance** standard for numeric attributes.  

### Example  
Suppose Patient A is 20-years-old with Na/K = 12, and Patient B is 30-years-old with Na/K = 8.  
What is the Euclidean distance between these two instances?

##### Solution  
Using the Euclidean distance formula:

$d_{\text{Euclidean}}(x, y) = \sqrt{\sum_{i}(x_i - y_i)^2}$
 $\text{where:}$
  $x = x1, x2, . . . , xm$
  $y = y1, y2, . . . , ym$
  $\text{represent the m attribute values of two records}$

For this example (Age and Na/K ratio):
$$
d_{\text{Euclidean}}(A, B)
= \sqrt{(20 - 30)^2 + (12 - 8)^2}
= \sqrt{100 + 16}
= 10.77
$$


 Categorical: use **different(x,y)** → 0 if equal, 1 if different.  

 **Normalization needed**: Min-Max or Z-score to prevent one variable dominating the distance.  
 
 $\text{Min–Max Normalization} = \frac{X - \min(X)}{\max(X) - \min(X)} \quad\quad$ 
 
$\text{Z-Score Standardization} = \frac{X - \text{mean}(X)}{\text{standard deviation}(X)}$



## Choosing k
- Small k → high variance, overfitting, sensitive to noise.  
- Large k → high bias, oversmoothing.  
- Choose via cross-validation.  
[^1]

## Voting Methods
- **Unweighted voting:** each of k neighbors votes equally.  
- **Weighted voting:** closer neighbors get more importance ($\text{weight}= \frac{1} {d^2}$). Avoids ties.  

## Stretching the Axes (Attribute Importance)
- Multiply variables by $\text{weight}=z_j$ to increase/decrease importance ( larger $z_j$ is associated with more important axis).  
- zj chosen via cross-validation or domain expertise.  
[^1] [^2]

## Database Considerations
- Training set must be balanced and representative.  
- May reduce training examples to boundary points if memory limited.  


## kNN for Estimation
- Uses **locally weighted averaging**, $\text{weight}= \frac{1} {d^2}$.  

[^1]: Cross-validation selects a random subset of data from the
	training set and determines the set of z1, z2, ..., zm that minimize
	the classification error on the test set

[^2]: Alternately, we may call upon domain experts to recommend
	values for z1, z2, ..., zm.
	Using either approach the k-Nearest Neighbor algorithm may be
	made more precise
