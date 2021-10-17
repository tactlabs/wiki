# Pretty Metrics

## Classifier:
### SGDC Classifier
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

### 
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




