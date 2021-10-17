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

### 3) LabelPropagation 
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

### 4) Random Forest Classifier
Reference Links:
- https://towardsai.net/p/machine-learning/why-choose-random-forest-and-not-decision-trees
-  https://medium.datadriveninvestor.com/random-forest-pros-and-cons-c1c42fb64f04

Pros:
- Robust to outliers.
- Works well with non-linear data.
- Lower risk of overfitting.
- Runs efficiently on a large dataset.
- Better accuracy than other classification algorithms.
- Random Forests can be used for both classification and regression tasks
- Random Forests can handle linear and non-linear relationships well

Cons:
- Slow Training
- Random forests are found to be biased while dealing with categorical variables.
- Not suitable for linear methods with a lot of sparse features
- Random Forests can be computationally intensive for large datasets
- Random forest is like a black box algorithm, you have very little control over what the model does.
- Random Forests are not easily interpretable. They provide feature importance but it does not provide complete visibility into the coefficients as linear regression.

### 5) GradientBoostingClassifier 
Reference Links:
- https://blog.paperspace.com/gradient-boosting-for-classification/

Pros:
- Build trees one at a time, where each new tree helps to correct errors made by previously trained tree. 
- With each tree added, the model becomes even more expressive. 
- Lots of flexibility - can optimize on different loss functions and provides several hyper parameter tuning options that make the function fit very flexible.
- Often provides predictive accuracy that cannot be trumped.
- No data pre-processing required - often works great with categorical and numerical values as is.

Cons:
- GradientBoostingClassifier training generally takes longer because of the fact that trees are built sequentially.
- Gradient Boosting Models will continue improving to minimize all errors. This can overemphasize outliers and cause overfitting.
- Computationally expensive - often require many trees (>1000) which can be time and memory exhaustive.
- Less interpretative in nature, although this is easily addressed with various tools.
- The high flexibility results in many parameters that interact and influence heavily the behavior of the approach (number of iterations, tree depth, regularization parameters, etc.). This requires a large grid search during tuning.

### 6) AdaBoostClassifier             
Reference Links:
- https://www.jigsawacademy.com/blogs/data-science/adaboost/

Pros:
- AdaBoost has many advantages due to its ease of use and less parameter tweaking when compared with the SVM algorithms.
- Plus AdaBoost can be used with SVM though theoretically, overfitting is not a feature of AdaBoost applications, perhaps because the parameters are not optimized jointly and the learning process is slowed due to estimation stage-wise. This link is useful to understand mathematics. 
- The flexible AdaBoost can also be used for accuracy improvement of weak classifiers and cases in image/text classification.

Cons:
- AdaBoost uses a progressively learning boosting technique. Hence high-quality data is needed in examples of AdaBoost vs Random Forest. 
- It is also very sensitive to outliers and noise in data requiring the elimination of these factors before using the data
- It is also much slower than the XGBoost algorithm.

### 7) BaggingClassifier
Pros:
- Helps in the reduction of variance, hence eliminating the overfitting of models in the procedure.
- Net error is evaluated in each learning steps. It works good with interactions.
- Boosting technique takes care of the weightage of the higher accuracy sample and lower accuracy sample and then gives the combined results.
- Boosting technique helps when we are dealing with bias or underfitting in the data set.

Cons:
- Introduces a loss of interpretability of a model.
- Bagging is not helpful in case of bias or underfitting in the data.
- Bagging ignores the value with the highest and the lowest result which may have a wide difference and provides an average result.

### 8) BernoulliNB 
Reference Links:
- https://iq.opengenus.org/bernoulli-naive-bayes/

Pros:
- They are extremely fast as compared to other classification models
- As in Bernoulli Naive Bayes each feature is treated independently with binary values only, it explicitly gives penalty to the model for non-occurrence of any of the features which are necessary for predicting the output y. And the other multinomial variant of Naive Bayes ignores this features instead of penalizing.
- In case of small amount of data or small documents(for example in text classification), Bernoulli Naive Bayes gives more accurate and precise results as compared to other models.
- It is fast and are able to make to make real-time predictions
- It can handle irrelevant features nicely

Cons:
- Being a naive(showing a lack of experience) classifier, it sometimes makes a strong assumption based on the shape of data
- If at times the features are dependent on each other then Naive Bayes assumptions can affect the prediction and accuracy of the model and is sensitive to the given input data.
- If there is a categorial variable which is not present in training dataset, it results in zero frequency problem. This problem can be easily solved by Laplace estimation.

### 9) Linear Discriminant Analysis 

Reference Links:
- https://medium.com/analytics-vidhya/pros-and-cons-of-popular-supervised-learning-algorithms-d5b3b75d9218
- https://www.knowledgehut.com/blog/data-science/linear-discriminant-analysis-for-machine-learning

Pros:
- It is simple, fast and portable algorithm. It still beats some algorithms (logistic regression) when its assumptions are met.
- It uses information from both the features to create a new axis which in turn minimizes the variance and maximizes the class distance of the two variables.
- Linear decision boundary fast classification easy to implement. 

Cons:
-  It requires normal distribution assumption on features/predictors.
- Sometimes not good for few categories variables.
- Gaussian assumptions training time complex matix ops.


### 10) GaussianNB
Reference Links:
- https://www.upgrad.com/blog/naive-bayes-classifier/
- https://www.kaggle.com/c/springleaf-marketing-response/discussion/16639

Pros:
- This algorithm works very fast and can easily predict the class of a test dataset. 
- You can use it to solve multi-class prediction problems as it's quite useful with them.
- Naive Bayes classifier performs better than other models with less training data if the assumption of independence of features holds. 
- If you have categorical input variables, the Naive Bayes algorithm performs exceptionally well in comparison to numerical variables. 
- It's can be easily trained even with small Dataset.

Cons:
- If your test data set has a categorical variable of a category that wasn't present in the training data set, the Naive Bayes model will assign it zero probability and won't be able to make any predictions in this regard. This phenomenon is called 'Zero Frequency,' and you'll have to use a smoothing technique to solve this problem.
- This algorithm is also notorious as a lousy estimator. So, you shouldn't take the probability outputs of 'predict_proba' too seriously. 
- It assumes that all the features are independent. While it might sound great in theory, in real life, you'll hardly find a set of independent features. 
- It consider every feature independent which is not the case everytime.
- Limited Application Case

### 11) DecisionTreeClassifier

Reference Links:
- https://dhirajkumarblog.medium.com/top-5-advantages-and-disadvantages-of-decision-tree-algorithm-428ebd199d9a

Pros:
- Compared to other algorithms decision trees requires less effort for data preparation during pre-processing.
- A decision tree does not require normalization of data.
- A decision tree does not require scaling of data as well.
- Missing values in the data also do NOT affect the process of building a decision tree to any considerable extent.
- A Decision tree model is very intuitive and easy to explain to technical teams as well as stakeholders.

Cons:
- A small change in the data can cause a large change in the structure of the decision tree causing instability.
- For a Decision tree sometimes calculation can go far more complex compared to other algorithms.
- Decision tree often involves higher time to train the model.
- Decision tree training is relatively expensive as the complexity and time has taken are more.
- The Decision Tree algorithm is inadequate for applying regression and predicting continuous values.

