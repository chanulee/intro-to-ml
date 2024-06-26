day 1 [[intro-to-ml-01]]
day 3 [[intro-to-ml-03]]

### Logistic regression
Including Type variable into numerical prediction model
Really useful, but how can I add it to logistic regression.
*How can I do this?*

One variable per option!
0~7 to each type - not good because it happens to have an order
#### One-hot encoding
Category into numeric value
redundant
Normalize it before.

#### How about non-linear?
![[Screenshot 2024-06-25 at 2.16.38 PM.png]]
It's not ease graph of 0 to 1 -> go up and down
This is why it's important to build non-linear models
#### Decision Tree 
![[Screenshot 2024-06-25 at 2.23.06 PM.png]]
Very difficult to find optimised and efficient decision tree
so we use greedy algorithm -> the most simple and impactful question goes up
They can have more than 2 but it's nice that useful as we can make several layers

good for understanding what model is saying. What it means.
They can deal with any type of data
classification tool or regression tool - both possible, flexible

![[Screenshot 2024-06-25 at 2.38.58 PM.png]]

## Evaluation and Improving performance
How do we compare different ML methods for the same task?
- performance metrics
- for example, regression and classification need different technique
### Evaluating Regression models
R2  for assessing the fit between a linear model and the data.
A good model would have R2 close to 1.
![[Screenshot 2024-06-25 at 2.42.37 PM.png]]
- difference between f(x) and x
- Ratio: SSres smaller the good

In machine learning, actual performance on non-test data
#### Cross validation
K = 5 or 10 often used
depends on how much training data
Most of the time, R2 is good way
<-> test on training data - overfitting (R2 0.9)
less tree depth = R2 gets better (0.4)
test on test data, connect all the data from sampler = final R2

Question on overall decision making on the models: How should we determine the parameters of tree model (in this case) - is it trying each several numbers and comparing those R2 results? Or even what model to use?

- Cross validation: Have a way to compare the model before actually training them
- R2 is a go-to way to compare these ![[Screenshot 2024-06-25 at 3.18.42 PM.png]]
#### Metrics for classification
Based on confusion matrix
![[Screenshot 2024-06-25 at 3.22.47 PM.png]]
- y is label (really positive or negative)
- 'hat' is prediction
- True / False - Positive / Negative
- N+ is number of positive
- Types of metrics ![[Screenshot 2024-06-25 at 3.23.36 PM.png]]
- Sensitivity and Specificity is important. Those two are complimentary. High in one, low in one.
- Why don't we use accuracy as a ultimate parameter?
	- This works well when the data is **balanced**.
	- Most important thing can be other metrics - test for very rare disease...
- In terms of numbers...![[Screenshot 2024-06-25 at 3.26.48 PM.png]]
- Receiver operating characteristic![[Screenshot 2024-06-25 at 3.28.05 PM.png]]
- Graph of nice overview
- Area under the curve
- We have to choose in between sensitivity and specificity. 
- ![[Screenshot 2024-06-25 at 3.29.46 PM.png]]
- AUC higher the better

## How do we Improve?
![[Screenshot 2024-06-25 at 3.36.38 PM.png]]
Let's say we're predicting numbers.
Two ways of going bad.
- Bias
	- Model is too simple
	- **consistant off-target**![[Screenshot 2024-06-25 at 3.39.09 PM.png]]
- High Variance
	- Overfitting
- ![[Screenshot 2024-06-25 at 3.42.25 PM.png]]
- high variance and high bias doesn't really occur often![[Screenshot 2024-06-25 at 3.43.51 PM.png]]
### What can we do to improve performance?
- ![[Screenshot 2024-06-25 at 3.47.30 PM.png]]
	- Dimensionality reduction: we will take every feature, but moving them into lower dimension
- Explore more models using different algorithms
- ![[Screenshot 2024-06-25 at 3.50.59 PM.png]]
	- Comparing different methods
	- ![[Screenshot 2024-06-25 at 3.52.44 PM.png]]
		- reducing depth (simple way)
#### Ensemble Methods
Combining multiple different models to vote, average...