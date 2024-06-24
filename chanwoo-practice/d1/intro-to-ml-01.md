## What is Machine Learning?
- Identifing **patterns** = unsupervised learning
- Training **models** using data to make prediction = supervised learning
- Neural Network = more flexible and lead to more complex ones like LLM = deep learning
- Machine Learning is about data driven predictions
![[Screenshot 2024-06-24 at 2.18.53 PM.png]]
![[Screenshot 2024-06-24 at 2.19.47 PM.png]]
![[Screenshot 2024-06-24 at 2.20.54 PM.png]]
## 4 types of Data
### Categorical Data
No numerical relationship between values
- **Nominal Data**
- **Ordinal Data**
### Quantitative Data
Numerical data from count and measurement
- **Discrete Data**
	Specific numbers / not continuous
	number of kids, shoe sizes
- **Continuous data**

- Features: column (or dimension even) in a dataset

Example dataset - IRIS
- Each columns are Continuous data (size)
- Name of Iris = categorical and nominal data
## Learnings
### Unsupervised learning
- To discover new knowledge
	- Dimensionality reduction
	- self organizing map (project a data)
	- clustering
- Clustering
	- usually used in exploratory data mining
	- What do we define 'similar'?
	- RGB (3 dimentional data) = color
	- **Feature based**
		- this type of clustering algorithm requires the individual data points to be represented by feature vectors.
	- **Distance based**
		- requires a matrix where each element represents the distance (or similarity) between pairs of data points
	- Output
		- flat: label
		- Hierarchical: tree
	- k-means clustering = feature based
		- k=integar, number of clusters
		- n observations (number of datapoints) k clusters (number of groups), based in means distance (center)
### Supervised Learning
- Predicting a function
	- feature=input=x vectors to target=output data=y
	- usually datasets comes with predetermined y
	- y is a quantative value = regression
	- y is categorical variable = classification
	- some algorithms can deal with both
#### Regression
- Linear regression: optimising and fitting a linear function
	- y=ax+b -> predict a and b
	- minimized sum of squared errors
	- x and y can be 2 dimension, as the linear function can just be plane
	- regularization 
		- push the coefficience to zero
		- smaller coefficience = more stabilized.
		- if it's 0, that feature is not related to the prediction
#### Classification = Logistic Regression
- If binary classification - 0 and 1
- pobability of certain data being class 1
- we can fit a logit (sigmoid) function ![[Screenshot 2024-06-24 at 3.47.19 PM.png]]
- Apply a threshold on this regression