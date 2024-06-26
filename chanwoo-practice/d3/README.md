day 1 [[intro-to-ml-01]]
day 2 [[intro-to-ml-02]]

### What can we do to improve performance?
- Advantageous to limit the features to be involved
- low row, lots of columns = large p (parameter) + small n -> lots of coefficient, over-fitting!
- feature selection = which of features have certain information, making the model more explainable
- dimensionality reduction = still the same features
- regularisation (objectively & automatically)

#### Feature Selection
- A good set of informative features would all be strongly correlated with the target, but not correlated with each other (same overlapping information)
- Feature Selection orange project -> 52 features, 20 countries(instances)
	- with linear regression, it just overfitted.
	- Correlation widget
	- If human choose some features that shows visible (to human) correlation, is it possible for machines to find a hidden pattern? or does this mean that ML cannot find unknown patterns?
		- By sight / simple correlation
		- Maybe other useful stuff is hiding
		- This leads to **regularization** 
#### Regularization
- coefficient towards 0
- Lasso regression L1
	- L2 = proportional to square (they never become exact 0, they still exist in the model)
	- elastic = mixing L1 and L2 with certain %
- alpha = strength, control this
- Weight and threshold?
	- Special kind of fitting with the model
	- penalty applied
- ![[Screenshot 2024-06-26 at 2.29.30 PM.png]]
#### Ensemble Methods
- multiple weak learners
- same type
- We have to choose
	- base model
	- how they're combined
		- sequential
		- stacking
		- bagging
- Bagging
	- bootstrap aggregating
	- parallel
	- every version of models sees slightly different data and built slightly differently
	- Bootstrap sampling
		- everytime it changes a little bit
		- create multiple datasets
	- Popular application / method is **random forest**
		- Ensemble of *trees*, built from different Bootstrap sample
		- Random subspace of features (picking 6 of 10)
		- they are exploring different aspects of the problem
		- Tree is much more interpretable than forest
		- 100 is mostly used number
		- off the shelf standard setting is going to do a good job

## Neural Network and Deep Learning
### Neural Network
- Inspired by nature
- Important component: Many inputs to the cell, signal processed, and output through Axon
- Perceptron (1958)
	- ![[Screenshot 2024-06-26 at 3.11.31 PM.png]]
	- Computational model
	- weighted sum of multiple inputs (each being vector)
	- weighted sum and bias (threshold) to generate output
- On the higher level, it's single layer network
	- Could be useful for linear regression or something
- For non-linear stuffs, Multi-layer network (Multi-layer perceptron)
	- ![[Screenshot 2024-06-26 at 3.13.27 PM.png]]
	- 3 nodes inside the hidden layer (it's not actually hidden, we can manipulate it)
	- This is a 'feedforward' network. no loop here in the structure. (we generally don't want them)
	- hidden layer is 'representing' the previous information
	- Model will "discover" its own representation of the data that best fits the learning task
	- The problem is in **fitting**
		- Loads and loads of parameters.
		- we need to find values for weights.
		- m arcs and n neurons, so it's optimization in high dimensional space -> Gradient descent
	- Gradient Descent
		- optimisation method
		- at a point, moving to find a minimum lost function.
		- practically, stochastic Gradient Descent
		- ![[Screenshot 2024-06-26 at 3.22.35 PM.png]]
		- cost function = color
		- theta = logistic regression - coefficient
		- arrive at the combination of parameters
	- Backpropagation
		- start with output layer, move through back layer to determine gradient of the loss function
		- it requires me to have an activation function
			- countinuous activation functions!
			- ![[Screenshot 2024-06-26 at 3.28.50 PM.png]]
			- Different shapes of functions affects the model
	- Multi-layer network exercise
		- Wine = non-linear!
		- logistic = sigmoid
		- NN regularazoin thinning out some of the edges of ... ?
### Deep Learning
- Lots of layers
- supervised, unsupervised
- Unstructured Data
	- Images, Text, speech, music
	- not in a table columns...
- ![[Screenshot 2024-06-26 at 3.38.41 PM.png]]
- Pixels to features!
	- image into data is easy
	- but from that data, extracting useful information encoded ![[Screenshot 2024-06-26 at 3.39.39 PM.png]]
	- relationship between eyes, nose, ears ...
	- The idea of **convolution**
		- preserves relationships in time/space
		- ![[Screenshot 2024-06-26 at 3.41.49 PM.png]]
		- consist extracting data
	- Google Inception (2015)
		- image classification model![[Screenshot 2024-06-26 at 3.45.27 PM.png]]
		- large and small scale at the same time![[Screenshot 2024-06-26 at 3.46.06 PM.png]]
		- It allows to train the model and use this in other occasion
			- before it makes decision, we can sort of intercept the embeddings made by the network
			- random forest can get into embeddings, and there are lots of useful information in the embeddings.
			- capturing **relevant information**
			- we don't have to re-train the model, just use the existing one.