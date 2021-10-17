# Pretty Metrics

## Classifier:
### 1) SGDC Classifier
Reference links:
- https://medium.com/@divakar_239/stochastic-vs-batch-gradient-descent-8820568eada1
 
Pros:
- It is easier to fit into memory due to a single training sample being processed by the network.
- It is computationally fast as only one sample is processed at a time
- For larger datasets it can converge faster as it causes updates to the parameters more frequently.
- Due to frequent updates the steps taken towards the minima of the loss function have oscillations 
   which can help getting out of local minimums of the loss function (in case the computed position turns out to be the local minimum)

Cons:
- Due to frequent updates the steps taken towards the minima are very noisy.This can often lead the gradient descent into other directions.
- Also, due to noisy steps it may take longer to achieve convergence to the minima of the loss function
- Frequent updates are computationally expensive due to using all resources for processing one training sample at a time.
- It loses the advantage of vectorized operations as it deals with only a single example at a time

### 2) Logistic Regression
Reference Links:
- https://www.geeksforgeeks.org/advantages-and-disadvantages-of-logistic-regression/

Pros:
- Logistic regression is easier to implement, interpret, and very efficient to train.
- It makes no assumptions about distributions of classes in feature space.
- It can easily extend to multiple classes(multinomial regression) and a natural probabilistic view of class predictions.
- It not only provides a measure of how appropriate a predictor(coefficient size)is, but also its direction of association (positive or negative).
- It is very fast at classifying unknown records.

Cons:
- If the number of observations is lesser than the number of features, Logistic Regression should not be used, otherwise, it may lead to overfitting.
- It constructs linear boundaries.
- The major limitation of Logistic Regression is the assumption of linearity between the dependent variable and the independent variables.
- It can only be used to predict discrete functions. Hence, the dependent variable of Logistic Regression is bound to the discrete number set.
- Non-linear problems can't be solved with logistic regression because it has a linear decision surface. Linearly separable data is rarely found in real-world scenarios.

### LabelPropagation 
Reference Links:
- https://towardsdatascience.com/how-to-get-away-with-few-labels-label-propagation-f891782ada5c

Pros:
- Easy to understand and implement
- Fast transformation and faster training as fewer samples mean less computation
- No parameter is required to be known beforehand
- Label propagation has advantages in its running time and amount of a priori information needed about the network structure 

Cons:
- The model might overfit to the remaining data
- Bias in the process of which data is labeled might lead to wrong decision boundaries of the model
- It produces no unique solution, but an aggregate of many solutions.
- Linear time complexity.
- Uncertainty and randomness in the label propagation process, which may affect the stability and accuracy of community detection.

### LogisticRegression
Reference Links:
-
Pros:
-
-
-
-

Cons:
-
-
-

### LogisticRegression
Reference Links:
-
Pros:
-
-
-
-

Cons:
-
-
-

### LogisticRegression
Reference Links:
-
Pros:
-
-
-
-

Cons:
-
-
-

### LogisticRegression
Reference Links:
-
Pros:
-
-
-
-

Cons:
-
-
-

### DecisionTreeClassifier
Reference Links:
- https://dhirajkumarblog.medium.com/top-5-advantages-and-disadvantages-of-decision-tree-algorithm-428ebd199d9a

Pros:
- Compared to other algorithms decision trees requires less effort for data preparation during pre-processing.
- A decision tree does not require normalization of data.
- A decision tree does not require scaling of data as well.
- Missing values in the data also do NOT affect the process of building a decision tree to any considerable extent.
- A Decision tree model is very intuitive and easy to explain to technical teams as well as stakeholders.

Cons:




