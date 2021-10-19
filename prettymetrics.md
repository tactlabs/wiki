# Pretty Metrics

## Classifier:
### 1) SGDC Classifier

 
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

Reference links:
  * [https://medium.com/@divakar_239/stochastic-vs-batch-gradient-descent-8820568eada1](https://medium.com/@divakar_239/stochastic-vs-batch-gradient-descent-8820568eada1)

### 2) Logistic Regression

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

Reference links:
  * [https://www.geeksforgeeks.org/advantages-and-disadvantages-of-logistic-regression/](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-logistic-regression/)

### 3) LabelPropagation 

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

Reference links:
  * [https://towardsdatascience.com/how-to-get-away-with-few-labels-label-propagation-f891782ada5c](https://towardsdatascience.com/how-to-get-away-with-few-labels-label-propagation-f891782ada5c)

### 4) Random Forest Classifier

Pros:
- Robust to outliers.
- Works well with non-linear data.
- Lower risk of overfitting.
- Runs efficiently on a large dataset.
- Better accuracy than other classification algorithms.
- Random Forests can be used for both classification and regression tasks
- Random Forests can handle linear and non-linear relationships well

Reference links:
  * [https://towardsai.net/p/machine-learning/why-choose-random-forest-and-not-decision-trees](https://towardsai.net/p/machine-learning/why-choose-random-forest-and-not-decision-trees)
  * [https://medium.datadriveninvestor.com/random-forest-pros-and-cons-c1c42fb64f04](https://medium.datadriveninvestor.com/random-forest-pros-and-cons-c1c42fb64f04)

Cons:
- Slow Training
- Random forests are found to be biased while dealing with categorical variables.
- Not suitable for linear methods with a lot of sparse features
- Random Forests can be computationally intensive for large datasets
- Random forest is like a black box algorithm, you have very little control over what the model does.
- Random Forests are not easily interpretable. They provide feature importance but it does not provide complete visibility into the coefficients as linear regression.

### 5) GradientBoostingClassifier 

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

Reference links:
  * [https://blog.paperspace.com/gradient-boosting-for-classification/](https://blog.paperspace.com/gradient-boosting-for-classification/)

### 6) AdaBoostClassifier             

Pros:
- AdaBoost has many advantages due to its ease of use and less parameter tweaking when compared with the SVM algorithms.
- Plus AdaBoost can be used with SVM though theoretically, overfitting is not a feature of AdaBoost applications, perhaps because the parameters are not optimized jointly and the learning process is slowed due to estimation stage-wise. This link is useful to understand mathematics. 
- The flexible AdaBoost can also be used for accuracy improvement of weak classifiers and cases in image/text classification.

Cons:
- AdaBoost uses a progressively learning boosting technique. Hence high-quality data is needed in examples of AdaBoost vs Random Forest. 
- It is also very sensitive to outliers and noise in data requiring the elimination of these factors before using the data
- It is also much slower than the XGBoost algorithm.

Reference links:
  * [https://www.jigsawacademy.com/blogs/data-science/adaboost/](https://www.jigsawacademy.com/blogs/data-science/adaboost/)

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

Reference links:
  * [1]()

### 8) BernoulliNB 

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

Reference links:
  * [https://iq.opengenus.org/bernoulli-naive-bayes/](https://iq.opengenus.org/bernoulli-naive-bayes/)

### 9) Linear Discriminant Analysis

Pros:
- It is simple, fast and portable algorithm. It still beats some algorithms (logistic regression) when its assumptions are met.
- It uses information from both the features to create a new axis which in turn minimizes the variance and maximizes the class distance of the two variables.
- Linear decision boundary fast classification easy to implement. 

Cons:
-  It requires normal distribution assumption on features/predictors.
- Sometimes not good for few categories variables.
- Gaussian assumptions training time complex matix ops.

Reference links:
  * [https://medium.com/analytics-vidhya/pros-and-cons-of-popular-supervised-learning-algorithms-d5b3b75d9218](https://medium.com/analytics-vidhya/pros-and-cons-of-popular-supervised-learning-algorithms-d5b3b75d9218)
  * [https://www.knowledgehut.com/blog/data-science/linear-discriminant-analysis-for-machine-learning](https://www.knowledgehut.com/blog/data-science/linear-discriminant-analysis-for-machine-learning)


### 10) GaussianNB

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

Reference links:
  * [https://www.upgrad.com/blog/naive-bayes-classifier/](https://www.upgrad.com/blog/naive-bayes-classifier/)
  * [https://www.kaggle.com/c/springleaf-marketing-response/discussion/16639](https://www.kaggle.com/c/springleaf-marketing-response/discussion/16639)

### 11) DecisionTreeClassifier

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

Reference links:
  * [https://dhirajkumarblog.medium.com/top-5-advantages-and-disadvantages-of-decision-tree-algorithm-428ebd199d9a](https://dhirajkumarblog.medium.com/top-5-advantages-and-disadvantages-of-decision-tree-algorithm-428ebd199d9a)

### 12) MLP Classifier

PROS:
- It can be applied to complex non-linear problems.
- It works well with large input data.
- It provides quick predictions after training.
- The same accuracy ratio can be achieved even with smaller data.
- It has the capability to learn models in real-time (on-line learning).

CONS:
- It is not known to what extent each independent variable is affected by the dependent variable. 
- Computations are difficult and time consuming.
- The proper functioning of the model depends on the quality of the training.
- It is sensitive to feature scaling
- It requires tuning a number of hyperparameters such as the number of hidden neurons, layers, and iterations.

Reference links:
* [https://www.researchgate.net/figure/Multilayer-Perceptron-Advantages-and-Disadvantages_tbl4_338950098] (https://www.researchgate.net/figure/Multilayer-Perceptron-Advantages-and-Disadvantages_tbl4_338950098)
* [https://scikit-learn.org/stable/modules/neural_networks_supervised.html]
(https://scikit-learn.org/stable/modules/neural_networks_supervised.html)

### 13) SVC

PROS:
- It works best for low-dimensional data.
- It provides specialized algorithms for computing the clusters by only computing a subset of the edges in the adjacency matrix.
- It is insensitive to penalty factor C.
- It has on-line learning ability.
- It restrains the effect of outliers

CONS:
- It requires an extra preprocessing step for high-dimensional data.
- It requires pricey storage for kernel matrix.
- It is a complex model with a number of parameters.
- Degraded ability of shrinking contour in profiling cluster.
- There is limited improvements on effiency for non-SVs retained.

Reference links:
* [http://www.scholarpedia.org/article/Support_vector_clustering] (http://www.scholarpedia.org/article/Support_vector_clustering)
* [https://www.researchgate.net/publication/267512308_Recent_Advances_in_Support_Vector_Clustering_Theory_and_Applications] (https://www.researchgate.net/publication/267512308_Recent_Advances_in_Support_Vector_Clustering_Theory_and_Applications)

### 14) KNeighborsClassifier

PROS:
- It is faster than most algorithms as it is simple and intutive.
- It does not require additional training when new data is provided.
- It is easy to implement it for multi-class problems.
- It does not explicitly build a model and thus there is no training step.
- It gives the user flexibility to choose the proximity.

CONS:
- It results in poor performance on imbalanced data.
- If the K value is chosen incorrectly, the model will be under or overfitted to the data.
- We must explicitly mention the Eucledian distance to find the proximity.
- It is imperative to scale the data.
- It demands for high memory.

Reference links:
* [https://towardsdatascience.com/k-nearest-neighbours-explained-7c49853633b6] (https://towardsdatascience.com/k-nearest-neighbours-explained-7c49853633b6)
* [https://towardsdatascience.com/k-nearest-neighbor-python-2fccc47d2a55] (https://towardsdatascience.com/k-nearest-neighbor-python-2fccc47d2a55)
* [https://www.fromthegenesis.com/pros-and-cons-of-k-nearest-neighbors/] (https://www.fromthegenesis.com/pros-and-cons-of-k-nearest-neighbors/)



##Regression

### 1) SVR:

PROS:
- It is robust to outliers.
- Decision model can be easily updated.
- It has excellent generalization capability, with high prediction accuracy.
- Its implementation is easy.
- It works really well with a clear margin of separation between classes


CONS:
- It doesn’t perform well when we have large data set because the required training time is higher
- It also doesn’t perform very well, when the data set has more noise i.e. target classes are overlapping
- SVM doesn’t directly provide probability estimates, these are calculated using an expensive five-fold cross-validation. It is included in the related SVC method of Python scikit-learn library.
- In cases where the number of features for each data point exceeds the number of training data samples, the SVM will underperform.
- Choosing an appropriate Kernel function is difficult: Choosing an appropriate Kernel function (to handle the non-linear data) is not an easy task. It could be tricky and complex. In case of using a high dimension Kernel, you might generate too many support vectors which reduce the training speed drastically. 

Reference links:
  * [https://medium.com/coinmonks/support-vector-regression-or-svr-8eb3acf6d0ff](https://medium.com/coinmonks/support-vector-regression-or-svr-8eb3acf6d0ff)
  * [https://medium.com/analytics-vidhya/machine-learning-support-vector-regression-181aea35bedf](https://medium.com/analytics-vidhya/machine-learning-support-vector-regression-181aea35bedf)
  * [https://medium.com/swlh/support-vector-regression-explained-for-beginners-2a8d14ba6e5d](https://medium.com/swlh/support-vector-regression-explained-for-beginners-2a8d14ba6e5d)
  * [https://medium.com/@bhartendudubey/what-is-support-vector-regression-svr-760b501b6141](https://medium.com/@bhartendudubey/what-is-support-vector-regression-svr-760b501b6141)
  * [https://towardsdatascience.com/unlocking-the-true-power-of-support-vector-regression-847fd123a4a0](https://towardsdatascience.com/unlocking-the-true-power-of-support-vector-regression-847fd123a4a0)
  * [https://towardsdatascience.com/support-vector-regression-svr-one-of-the-most-flexible-yet-robust-prediction-algorithms-4d25fbdaca60](https://towardsdatascience.com/support-vector-regression-svr-one-of-the-most-flexible-yet-robust-prediction-algorithms-4d25fbdaca60)

### 2) Bagging Regressor:

PROS:
- Bagging method helps when we face variance or overfitting in the model. It provides an environment to deal with variance by using N learners of same size on same algorithm.
- It also performs well on high-dimensional data. 
- The missing values in the dataset do not affect the performance of the algorithm.
- The biggest advantage of bagging is that multiple weak learners can work better than a single strong learner.
- It provides stability and increases the machine learning algorithm’s accuracy that is used in statistical classification and regression.
- During the sampling of train data, there are many observations which overlaps. So, the combination of these learners helps in overcoming the high variance.

CONS:
- It gives its final prediction based on the mean predictions from the subset trees, rather than outputting the precise values for the classification or regression model.
- It may result in high bias if it is not modelled properly and thus may result in underfitting.
- Since we must use multiple models, it becomes computationally expensive and may not be suitable in various use cases.
- It introduces a loss of interpretability of a model
- Bagging ignores the value with the highest and the lowest result which may have a wide difference and provides an average result.

Reference links:
  * [https://medium.com/swlh/boosting-and-bagging-explained-with-examples-5353a36eb78d](https://medium.com/swlh/boosting-and-bagging-explained-with-examples-5353a36eb78d)
  * [https://medium.com/rapids-ai/100x-faster-machine-learning-model-ensembling-with-rapids-cuml-and-scikit-learn-meta-estimators-d869788ee6b1](https://medium.com/rapids-ai/100x-faster-machine-learning-model-ensembling-with-rapids-cuml-and-scikit-learn-meta-estimators-d869788ee6b1)
  * [https://medium.com/all-about-ml/bagging-random-forests-and-boosting-8c728e91a85d](https://medium.com/all-about-ml/bagging-random-forests-and-boosting-8c728e91a85d)
  * [https://medium.com/@uttam94/bagging-and-boosting-3fabc20bd9a5](https://medium.com/@uttam94/bagging-and-boosting-3fabc20bd9a5)
  * [https://towardsdatascience.com/ensemble-methods-bagging-boosting-and-stacking-c9214a10a205](https://towardsdatascience.com/ensemble-methods-bagging-boosting-and-stacking-c9214a10a205)
  * [https://medium.com/@ruhi3929/bagging-and-boosting-method-c036236376eb](https://medium.com/@ruhi3929/bagging-and-boosting-method-c036236376eb)


### 3) NuSVR:

Pros:
- Parameters are provided for adjustment of the vector machine that is used to assist in estimation of the regression problem
- This model is great for predicting continuous features with a lot of features that may or may not be incredibly important to our target
- It is robust to outliers.
- Decision model can be easily updated.
- It has excellent generalization capability, with high prediction accuracy.
- Its implementation is easy.

Cons:
- Not suitable for large data sets.
- The required training time is higher in case of large data sets.
- Does not perform very well when the data set has more noise
- In cases where the number of features for each data point exceeds the number of training data samples, it'll underperform.
- Choosing a “good” kernel function is not easy.

Reference links:
  * [https://towardsdatascience.com/15-lesser-known-useful-sklearn-models-you-should-use-now-a1a566e680a6](https://towardsdatascience.com/15-lesser-known-useful-sklearn-models-you-should-use-now-a1a566e680a6)
  * [https://stackoverflow.com/questions/20507809/nusvr-vs-svr-in-scikit-learn](https://stackoverflow.com/questions/20507809/nusvr-vs-svr-in-scikit-learn)
  * [https://www.programcreek.com/python/example/99109/sklearn.svm.NuSVR\](https://www.programcreek.com/python/example/99109/sklearn.svm.NuSVR\)
  * [https://www.datatechnotes.com/2020/07/regression-example-with-nusvr-in-python.html](https://www.datatechnotes.com/2020/07/regression-example-with-nusvr-in-python.html)
  * [https://www.kaggle.com/tunguz/trends-with-sklearn-nusvr](https://www.kaggle.com/tunguz/trends-with-sklearn-nusvr)


### 4) RandomForestRegressor:

Pros:
- Robust to outliers.
- Works well with non-linear data.
- Lower risk of overfitting.
- Runs efficiently on a large dataset.
- Better accuracy than other classification algorithms.

Cons:
- Random forests are found to be biased while dealing with categorical variables.
- Slow Training.
- Not suitable for linear methods with a lot of sparse features
- It requires much computational power as well as resources as it builds numerous trees to combine their outputs.
- Due to the ensemble of decision trees, it also suffers interpretability and fails to determine the significance of each variable.

Reference links:
  * [https://medium.com/swlh/random-forest-and-its-implementation-71824ced454f](https://medium.com/swlh/random-forest-and-its-implementation-71824ced454f)
  * [https://medium.com/@sametgirgin/random-forest-regression-in-5-steps-with-python-ee4259eca0de](https://medium.com/@sametgirgin/random-forest-regression-in-5-steps-with-python-ee4259eca0de)
  * [https://towardsdatascience.com/a-quick-and-dirty-guide-to-random-forest-regression-52ca0af157f8](https://towardsdatascience.com/a-quick-and-dirty-guide-to-random-forest-regression-52ca0af157f8)
  * [https://towardsdatascience.com/machine-learning-basics-random-forest-regression-be3e1e3bb91a](https://towardsdatascience.com/machine-learning-basics-random-forest-regression-be3e1e3bb91a)
  * [https://medium.datadriveninvestor.com/random-forest-regression-9871bc9a25eb](https://medium.datadriveninvestor.com/random-forest-regression-9871bc9a25eb)


### 5) XGBRegressor:

Pros:
- Effective with large data sets. 
- It do not need normalized features 
- It works well if the data is nonlinear, non-monotonic, or with segregated clusters.
- Boosting is a resilient and robust method that prevents and cubs over-fitting quite easily
- It comes with an easy to read and interpret algorithm, making most of its predictions easy to handle.

Cons:
- It can over-fit the data, especially if the trees are too deep with noisy data.
- It doesn’t work so well on sparse data, though, and very dispersed data can create some issues, as well. 
- If you need effect sizes, XGBoost won’t give them to you 
- The overall method is hardly scalable. 
- The estimators base their correctness on previous predictors, hence the procedure involves a lot of struggle to streamline. 

Reference links:
  * [https://towardsdatascience.com/predicting-electricity-consumption-with-xgbregressor-a11b71104754](https://towardsdatascience.com/predicting-electricity-consumption-with-xgbregressor-a11b71104754)
  * [https://towardsdatascience.com/predicting-weekly-hotel-cancellations-with-xgbregressor-d73eb74a8624](https://towardsdatascience.com/predicting-weekly-hotel-cancellations-with-xgbregressor-d73eb74a8624)
  * [https://medium.com/sfu-cspmp/xgboost-a-deep-dive-into-boosting-f06c9c41349](https://medium.com/sfu-cspmp/xgboost-a-deep-dive-into-boosting-f06c9c41349)
  * [https://medium.com/mlearning-ai/forecast-with-xgboost-model-in-python-87d4b6cada98](https://medium.com/mlearning-ai/forecast-with-xgboost-model-in-python-87d4b6cada98)
  * [https://medium.com/@gautam.karmakar/xgboost-model-to-win-kaggle-e12b35cd1aad](https://medium.com/@gautam.karmakar/xgboost-model-to-win-kaggle-e12b35cd1aad)


### 6) GradientBoostingRegressor 

Pros:
- Often provides predictive accuracy that cannot be trumped.
- Lots of flexibility - can optimize on different loss functions 
- Provides several hyper parameter tuning options that make the function fit very flexible.
- No data pre-processing required - often works great with categorical and numerical values as is.
- Handles missing data - imputation not required.

Cons:
- It will continue improving to minimize all errors. This can overemphasize outliers and cause overfitting.
- Computationally expensive - often require many trees (>1000) which can be time and memory exhaustive.
- The high flexibility results in many parameters that interact and influence heavily the behavior of the approach (number of iterations, tree depth, regularization parameters, etc.). This requires a large grid search during tuning.
- Less interpretative in nature, although this is easily addressed with various tools.
- Sensitive to outliers

Reference links:
  * [https://medium.datadriveninvestor.com/gradient-boosting-for-regression-539fa8aa4b00](https://medium.datadriveninvestor.com/gradient-boosting-for-regression-539fa8aa4b00)
  * [https://medium.com/analytics-vidhya/minimize-your-errors-by-learning-gradient-boosting-regression-2c002c65a064](https://medium.com/analytics-vidhya/minimize-your-errors-by-learning-gradient-boosting-regression-2c002c65a064)
  * [https://medium.com/analytics-vidhya/introduction-to-the-gradient-boosting-algorithm-c25c653f826b](https://medium.com/analytics-vidhya/introduction-to-the-gradient-boosting-algorithm-c25c653f826b)
  * [https://medium.com/@ladkarsamisha123/gradient-boosting-in-machine-learning-visually-explained-55b8c2099d19](https://medium.com/@ladkarsamisha123/gradient-boosting-in-machine-learning-visually-explained-55b8c2099d19)
  * [https://ankitnitjsr13.medium.com/gradient-boosting-algorithm-800e5b2bb3e4](https://ankitnitjsr13.medium.com/gradient-boosting-algorithm-800e5b2bb3e4)

### 7) HistGradientBoostingRegressor

Pros:
- This estimator is much faster than GradientBoostingRegressor for big datasets
- This estimator has native support for missing values
- When predicting, samples with missing values are assigned to the left or right child consequently
- It is used for training faster decision trees used in the gradient boosting ensemble
- It performs so well across a wide range of datasets in practice.

Cons:
- GBMs are more sensitive to overfitting if the data is noisy.
- Training generally takes longer because of the fact that trees are built sequentially.
- GBMs are harder to tune than RF.
- Can overemphasize outliers 
- Sensitive to outliers

Reference links:
  * [https://medium.com/@mqofori/a-first-look-at-sklearns-histgradientboostingclassifier-9f5bea611c6a](https://medium.com/@mqofori/a-first-look-at-sklearns-histgradientboostingclassifier-9f5bea611c6a)
  * [https://medium.com/mlearning-ai/how-i-improved-my-score-on-kaggles-june-2021-tabular-competition-by-using-bab6bbd0d803](https://medium.com/mlearning-ai/how-i-improved-my-score-on-kaggles-june-2021-tabular-competition-by-using-bab6bbd0d803)
  * [https://towardsdatascience.com/the-10-best-new-features-in-scikit-learn-0-24-f45e49b6741b](https://towardsdatascience.com/the-10-best-new-features-in-scikit-learn-0-24-f45e49b6741b)
  * [https://towardsdatascience.com/new-features-in-scikit-learn-f0ceb7e9d2ad](https://towardsdatascience.com/new-features-in-scikit-learn-f0ceb7e9d2ad)
  * [https://www.kaggle.com/carlmcbrideellis/histogram-gradient-boosting-regression-example](https://www.kaggle.com/carlmcbrideellis/histogram-gradient-boosting-regression-example)
  * [https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.HistGradientBoostingRegressor.html](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.HistGradientBoostingRegressor.html)
  * [https://machinelearningmastery.com/histogram-based-gradient-boosting-ensembles/](https://machinelearningmastery.com/histogram-based-gradient-boosting-ensembles/)

### 8) PoissonRegressor

Pros:
- The Poisson model is estimated by the maximum likelihood method, the estimates are adapted to the actual data. 
- It generally gives a better estimate of the counts for each record
- The Poisson model has a minimum value of 0. It will not predict negative values. This makes it
ideal for a distribution in which the mean or the most typical value is close to 0.
- This model is appropriate for counts of rare events, such as crime incidents
- Poisson models with robust standard errors are increasingly being recommended for situations in which it makes conceptual sense to model the log mean of the outcome

Cons:
- It makes strong assumptions regarding the distribution of the underlying data
- You'd get a loss of efficiency from using a Poisson regression compared to something more appropriate.
- A Poisson distribution would allow for nonzero probability only
- It can produce out-of-range predictions.
- Poisson regression assumes that the mean and variance are the same

Reference links:
  * [https://medium.com/@kn12/poisson-regression-implementation-python-28d15e95dc15](https://medium.com/@kn12/poisson-regression-implementation-python-28d15e95dc15)
  * [https://timeseriesreasoning.com/contents/poisson-regression-model/](https://timeseriesreasoning.com/contents/poisson-regression-model/)
  * [https://www.kaggle.com/gauravduttakiit/explore-the-poisson-regression](https://www.kaggle.com/gauravduttakiit/explore-the-poisson-regression)
  * [https://ml.dask.org/modules/generated/dask_ml.linear_model.PoissonRegression.html](https://ml.dask.org/modules/generated/dask_ml.linear_model.PoissonRegression.html)
  * [https://www.statisticshowto.com/poisson-regression/](https://www.statisticshowto.com/poisson-regression/)

### 9) LGBMRegressor

Pros:
- Faster training speed and higher efficiency: Light GBM use histogram based algorithm i.e it buckets continuous feature values into discrete bins which fasten the training procedure.
- Lower memory usage: Replaces continuous values to discrete bins which result in lower memory usage.
- Better accuracy than any other boosting algorithm: It produces much more complex trees by following leaf wise split approach rather than a level-wise approach which is the main factor in achieving higher accuracy. However, it can sometimes lead to overfitting which can be avoided by setting the max_depth parameter.
- Compatibility with Large Datasets: It is capable of performing equally good with large datasets with a significant reduction in training time as compared to XGBOOST.
- Parallel learning supported.
- more accurate and time-saving

Cons:
- Narrow user base and less documentation availability
- It is not advisable to use LGBM on small datasets
- It is sensitive to overfitting and can easily overfit small data
- There is no threshold on the number of rows
- Need to use tuning to avoid overfitting, or speeding up the task and to achieve good accuracy.

Reference links:
  * [https://machinelearningmastery.com/light-gradient-boosted-machine-lightgbm-ensemble/](https://machinelearningmastery.com/light-gradient-boosted-machine-lightgbm-ensemble/)
  * [https://www.programcreek.com/python/example/88794/lightgbm.LGBMRegressor](https://www.programcreek.com/python/example/88794/lightgbm.LGBMRegressor)
  * [https://lightgbm.readthedocs.io/en/latest/pythonapi/lightgbm.LGBMRegressor.html](https://lightgbm.readthedocs.io/en/latest/pythonapi/lightgbm.LGBMRegressor.html)
  * [https://medium.com/@pushkarmandot/https-medium-com-pushkarmandot-what-is-lightgbm-how-to-implement-it-how-to-fine-tune-the-parameters-60347819b7fc](https://medium.com/@pushkarmandot/https-medium-com-pushkarmandot-what-is-lightgbm-how-to-implement-it-how-to-fine-tune-the-parameters-60347819b7fc)
  * [https://medium.com/analytics-vidhya/lightgbm-for-regression-with-categorical-data-b08eaff501d1](https://medium.com/analytics-vidhya/lightgbm-for-regression-with-categorical-data-b08eaff501d1)

### 10) Decision Tree Regression : 	
   			   
Pros:
- The decision tree model can be used for both classification and regression problems, and it is easy to interpret, understand, and visualize. 
- The output of a decision tree can also be easily understood. 
- Compared with other algorithms, data preparation during pre-processing in a decision tree requires less effort and does not require normalization of data. 
- The implementation can also be done without scaling the data. 
- A decision tree is one of the quickest ways to identify relationships between variables and the most significant variable. 

Cons:
1) Overfitting is one of the practical difficulties for decision tree models. It happens when the learning algorithm continues developing hypotheses that reduce the training set error but at the cost of increasing test set error. But this issue can be resolved by pruning and setting constraints on the model parameters. 
2) Decision trees cannot be used well with continuous numerical variables. 
3) A small change in the data tends to cause a big difference in the tree structure, which causes instability. 
4) Calculations involved can also become complex compared to other algorithms, and it takes a longer time to train the model. 
5) It is also relatively expensive as the amount of time taken and the complexity levels are greater.

Reference links:
  * [https://www.upgrad.com/blog/pros-and-cons-of-decision-tree-regression-in-machine-learning/](https://www.upgrad.com/blog/pros-and-cons-of-decision-tree-regression-in-machine-learning/)
  * [2]()
  * [3]()

### 11) LinearRegression 

Pros:
- Simple model : 
The Linear regression model is the simplest equation using which the relationship between the multiple predictor variables and predicted variable can be expressed.
- Computationally efficient : 
The modeling speed of Linear regression is fast as it does not require complicated calculations and runs predictions fast when the amount of data is large.
- Interpretability of the Output: 
The ability of Linear regression to determine the relative influence of one or more predictor variables to the predicted value when the predictors are independent of each other is one of the key reasons of the popularity of Linear regression. The model derived using this method can express the what change in the predictor variable causes what change in the predicted or target variable.

Cons :
- Overly-Simplistic:
The Linear regression model is too simplistic to capture real world complexity
- Linearity Assumption:
Linear regression makes strong assumptions that there is Predictor (independent) and Predicted (dependent) variables are linearly related which may not be the case.
- Severely affected by Outliers:
Outliers can have a large effect on the output, as the Best Fit Line tries to minimize the MSE for the outlier points as well, resulting in a model that is not able to capture the information in the data.
- Independence of variables :
Assumes that the predictor variables are not correlated which is rarely true. It is important to, therefore, remove multicollinearity (using dimensionality reduction techniques) because the technique assumes that there is no relationship among independent variables. In cases of high multicollinearity, two features that have high correlation will influence each other's weight and result in an unreliable model.
- Assumes Homoskedacity :
Linear regression looks at a relationship between the mean of the predictor/dependent variable and the predicted/independent variables and assumes constant variance around the mean which is unrealistic in most cases.
- Inability to determine Feature importance :
As discussed in the "Assumes independent variables" point, in cases of high multicollinearity, 2 features that have high correlation will affect each other's weight. 
If we run stochastic linear regression multiple times, the result may be different weights each time for these 2 features. So, it's we cannot really interpret the importance of these features.

Reference links:
  * [https://medium.com/@satyavishnumolakala/linear-regression-pros-cons-62085314aef0](https://medium.com/@satyavishnumolakala/linear-regression-pros-cons-62085314aef0)

### 12) LARS : 
			   
Pros:
- Computationally as fast as forward selection but may sometimes be more accurate.
- Numerically very efficient when the number of features is much larger than the number of data instances.
- It can easily be modified to produce solutions for other estimators.
- If two variables are almost equally correlated with the response, then their coefficients should increase at approximately the same rate. The algorithm thus behaves as intuition would expect, and also is more stable.
- It produces a full piecewise linear solution path, which is useful in cross-validation or similar attempts to tune the model.

Cons:
- LARS is highly sensitive to noise and can produce unpredictable results sometimes.
- Because LARS is based upon an iterative refitting of the residuals, it would appear to be especially sensitive to the effects of noise. This problem is discussed in detail by Weisberg in the discussion section of the Efron et al. (2004) Annals of Statistics article.
- Lack of long-term studies and mixed results on the current base of knowledge.
- Residual post-operative laxity still present
- Requires tissue remnants of the ACL to be used in reconstruction

Reference links:
  * [https://venali.medium.com/conventional-guide-to-supervised-learning-with-scikit-learn-least-angle-regression-generalized-11b4ce2dec89](https://venali.medium.com/conventional-guide-to-supervised-learning-with-scikit-learn-least-angle-regression-generalized-11b4ce2dec89)
  * [https://www.physio-pedia.com/Ligament_Augmentation_and_Reconstruction_System_(LARS)](https://www.physio-pedia.com/Ligament_Augmentation_and_Reconstruction_System_(LARS))


### 13) SGD : 	
REFERENCE LINKS:  
- https://www.quora.com/What-are-the-pro##Regression

### 1) SVR:

PROS:
- It is robust to outliers.
- Decision model can be easily updated.
- It has excellent generalization capability, with high prediction accuracy.
- Its implementation is easy.
- It works really well with a clear margin of separation between classes


CONS:
- It doesn’t perform well when we have large data set because the required training time is higher
- It also doesn’t perform very well, when the data set has more noise i.e. target classes are overlapping
- SVM doesn’t directly provide probability estimates, these are calculated using an expensive five-fold cross-validation. It is included in the related SVC method of Python scikit-learn library.
- In cases where the number of features for each data point exceeds the number of training data samples, the SVM will underperform.
- Choosing an appropriate Kernel function is difficult: Choosing an appropriate Kernel function (to handle the non-linear data) is not an easy task. It could be tricky and complex. In case of using a high dimension Kernel, you might generate too many support vectors which reduce the training speed drastically. 

Reference links:
  * [https://medium.com/coinmonks/support-vector-regression-or-svr-8eb3acf6d0ff](https://medium.com/coinmonks/support-vector-regression-or-svr-8eb3acf6d0ff)
  * [https://medium.com/analytics-vidhya/machine-learning-support-vector-regression-181aea35bedf](https://medium.com/analytics-vidhya/machine-learning-support-vector-regression-181aea35bedf)
  * [https://medium.com/swlh/support-vector-regression-explained-for-beginners-2a8d14ba6e5d](https://medium.com/swlh/support-vector-regression-explained-for-beginners-2a8d14ba6e5d)
  * [https://medium.com/@bhartendudubey/what-is-support-vector-regression-svr-760b501b6141](https://medium.com/@bhartendudubey/what-is-support-vector-regression-svr-760b501b6141)
  * [https://towardsdatascience.com/support-vector-regression-svr-one-of-the-most-flexible-yet-robust-prediction-algorithms-4d25fbdaca60](https://towardsdatascience.com/unlocking-the-true-power-of-support-vector-regression-847fd123a4a0)
  

### 2) Bagging Regressor:

PROS:
- Bagging method helps when we face variance or overfitting in the model. It provides an environment to deal with variance by using N learners of same size on same algorithm.
- It also performs well on high-dimensional data. 
- The missing values in the dataset do not affect the performance of the algorithm.
- The biggest advantage of bagging is that multiple weak learners can work better than a single strong learner.
- It provides stability and increases the machine learning algorithm’s accuracy that is used in statistical classification and regression.
- During the sampling of train data, there are many observations which overlaps. So, the combination of these learners helps in overcoming the high variance.

CONS:
- It gives its final prediction based on the mean predictions from the subset trees, rather than outputting the precise values for the classification or regression model.
- It may result in high bias if it is not modelled properly and thus may result in underfitting.
- Since we must use multiple models, it becomes computationally expensive and may not be suitable in various use cases.
- It introduces a loss of interpretability of a model
- Bagging ignores the value with the highest and the lowest result which may have a wide difference and provides an average result.

Reference links:
  * [https://medium.com/swlh/boosting-and-bagging-explained-with-examples-5353a36eb78d](https://medium.com/swlh/boosting-and-bagging-explained-with-examples-5353a36eb78d)
  * [https://medium.com/rapids-ai/100x-faster-machine-learning-model-ensembling-with-rapids-cuml-and-scikit-learn-meta-estimators-d869788ee6b1](https://medium.com/rapids-ai/100x-faster-machine-learning-model-ensembling-with-rapids-cuml-and-scikit-learn-meta-estimators-d869788ee6b1)
  * [https://medium.com/all-about-ml/bagging-random-forests-and-boosting-8c728e91a85d](https://medium.com/all-about-ml/bagging-random-forests-and-boosting-8c728e91a85d)
  * [https://medium.com/@uttam94/bagging-and-boosting-3fabc20bd9a5](https://medium.com/@uttam94/bagging-and-boosting-3fabc20bd9a5)
  * [https://towardsdatascience.com/ensemble-methods-bagging-boosting-and-stacking-c9214a10a205](https://towardsdatascience.com/ensemble-methods-bagging-boosting-and-stacking-c9214a10a205)
  * [https://medium.com/@ruhi3929/bagging-and-boosting-method-c036236376eb](https://medium.com/@ruhi3929/bagging-and-boosting-method-c036236376eb)

### 3) NuSVR:

Pros:
- Parameters are provided for adjustment of the vector machine that is used to assist in estimation of the regression problem
- This model is great for predicting continuous features with a lot of features that may or may not be incredibly important to our target
- It is robust to outliers.
- Decision model can be easily updated.
- It has excellent generalization capability, with high prediction accuracy.
- Its implementation is easy.

Cons:
- Not suitable for large data sets.
- The required training time is higher in case of large data sets.
- Does not perform very well when the data set has more noise
- In cases where the number of features for each data point exceeds the number of training data samples, it'll underperform.
- Choosing a “good” kernel function is not easy.

Reference links:
  * [https://towardsdatascience.com/15-lesser-known-useful-sklearn-models-you-should-use-now-a1a566e680a6](https://towardsdatascience.com/15-lesser-known-useful-sklearn-models-you-should-use-now-a1a566e680a6)
  * [https://stackoverflow.com/questions/20507809/nusvr-vs-svr-in-scikit-learn](https://stackoverflow.com/questions/20507809/nusvr-vs-svr-in-scikit-learn)
  * [https://www.datatechnotes.com/2020/07/regression-example-with-nusvr-in-python.html](https://www.programcreek.com/python/example/99109/sklearn.svm.NuSVR\)
  * [https://www.kaggle.com/tunguz/trends-with-sklearn-nusvr](https://www.kaggle.com/tunguz/trends-with-sklearn-nusvr)


### 4) RandomForestRegressor:

Pros:
- Robust to outliers.
- Works well with non-linear data.
- Lower risk of overfitting.
- Runs efficiently on a large dataset.
- Better accuracy than other classification algorithms.

Cons:
- Random forests are found to be biased while dealing with categorical variables.
- Slow Training.
- Not suitable for linear methods with a lot of sparse features
- It requires much computational power as well as resources as it builds numerous trees to combine their outputs.
- Due to the ensemble of decision trees, it also suffers interpretability and fails to determine the significance of each variable.

Reference links:
  * [https://medium.com/swlh/random-forest-and-its-implementation-71824ced454f](https://medium.com/swlh/random-forest-and-its-implementation-71824ced454f)
  * [https://medium.com/@sametgirgin/random-forest-regression-in-5-steps-with-python-ee4259eca0de](https://medium.com/@sametgirgin/random-forest-regression-in-5-steps-with-python-ee4259eca0de)
  * [https://towardsdatascience.com/a-quick-and-dirty-guide-to-random-forest-regression-52ca0af157f8](https://towardsdatascience.com/a-quick-and-dirty-guide-to-random-forest-regression-52ca0af157f8)
  * [https://towardsdatascience.com/machine-learning-basics-random-forest-regression-be3e1e3bb91a](https://towardsdatascience.com/machine-learning-basics-random-forest-regression-be3e1e3bb91a)
  * [https://medium.datadriveninvestor.com/random-forest-regression-9871bc9a25eb](https://medium.datadriveninvestor.com/random-forest-regression-9871bc9a25eb)


### 5) XGBRegressor:

Pros:
- Effective with large data sets. 
- It do not need normalized features 
- It works well if the data is nonlinear, non-monotonic, or with segregated clusters.
- Boosting is a resilient and robust method that prevents and cubs over-fitting quite easily
- It comes with an easy to read and interpret algorithm, making most of its predictions easy to handle.

Cons:
- It can over-fit the data, especially if the trees are too deep with noisy data.
- It doesn’t work so well on sparse data, though, and very dispersed data can create some issues, as well. 
- If you need effect sizes, XGBoost won’t give them to you 
- The overall method is hardly scalable. 
- The estimators base their correctness on previous predictors, hence the procedure involves a lot of struggle to streamline. 

Reference links:
  * [https://towardsdatascience.com/predicting-electricity-consumption-with-xgbregressor-a11b71104754](https://towardsdatascience.com/predicting-electricity-consumption-with-xgbregressor-a11b71104754)
  * [https://towardsdatascience.com/predicting-weekly-hotel-cancellations-with-xgbregressor-d73eb74a8624](https://towardsdatascience.com/predicting-weekly-hotel-cancellations-with-xgbregressor-d73eb74a8624)
  * [https://medium.com/sfu-cspmp/xgboost-a-deep-dive-into-boosting-f06c9c41349](https://medium.com/sfu-cspmp/xgboost-a-deep-dive-into-boosting-f06c9c41349)
  * [https://medium.com/mlearning-ai/forecast-with-xgboost-model-in-python-87d4b6cada98](https://medium.com/mlearning-ai/forecast-with-xgboost-model-in-python-87d4b6cada98)
  * [https://medium.com/@gautam.karmakar/xgboost-model-to-win-kaggle-e12b35cd1aad](https://medium.com/@gautam.karmakar/xgboost-model-to-win-kaggle-e12b35cd1aad)


### 6) GradientBoostingRegressor 

Pros:
- Often provides predictive accuracy that cannot be trumped.
- Lots of flexibility - can optimize on different loss functions 
- Provides several hyper parameter tuning options that make the function fit very flexible.
- No data pre-processing required - often works great with categorical and numerical values as is.
- Handles missing data - imputation not required.

Cons:
- It will continue improving to minimize all errors. This can overemphasize outliers and cause overfitting.
- Computationally expensive - often require many trees (>1000) which can be time and memory exhaustive.
- The high flexibility results in many parameters that interact and influence heavily the behavior of the approach (number of iterations, tree depth, regularization parameters, etc.). This requires a large grid search during tuning.
- Less interpretative in nature, although this is easily addressed with various tools.
- Sensitive to outliers

Reference links:
  * [https://medium.datadriveninvestor.com/gradient-boosting-for-regression-539fa8aa4b00](https://medium.datadriveninvestor.com/gradient-boosting-for-regression-539fa8aa4b00)
  * [https://medium.com/analytics-vidhya/minimize-your-errors-by-learning-gradient-boosting-regression-2c002c65a064](https://medium.com/analytics-vidhya/minimize-your-errors-by-learning-gradient-boosting-regression-2c002c65a064)
  * [https://medium.com/analytics-vidhya/introduction-to-the-gradient-boosting-algorithm-c25c653f826b](https://medium.com/analytics-vidhya/introduction-to-the-gradient-boosting-algorithm-c25c653f826b)
  * [https://medium.com/@ladkarsamisha123/gradient-boosting-in-machine-learning-visually-explained-55b8c2099d19](https://medium.com/@ladkarsamisha123/gradient-boosting-in-machine-learning-visually-explained-55b8c2099d19)
  * [https://ankitnitjsr13.medium.com/gradient-boosting-algorithm-800e5b2bb3e4](https://ankitnitjsr13.medium.com/gradient-boosting-algorithm-800e5b2bb3e4)
  

### 7) HistGradientBoostingRegressor

Pros:
- This estimator is much faster than GradientBoostingRegressor for big datasets
- This estimator has native support for missing values
- When predicting, samples with missing values are assigned to the left or right child consequently
- It is used for training faster decision trees used in the gradient boosting ensemble
- It performs so well across a wide range of datasets in practice.

Cons:
- GBMs are more sensitive to overfitting if the data is noisy.
- Training generally takes longer because of the fact that trees are built sequentially.
- GBMs are harder to tune than RF.
- Can overemphasize outliers 
- Sensitive to outliers

Reference links:
  * [https://medium.com/@mqofori/a-first-look-at-sklearns-histgradientboostingclassifier-9f5bea611c6a](https://medium.com/@mqofori/a-first-look-at-sklearns-histgradientboostingclassifier-9f5bea611c6a)
  * [https://medium.com/mlearning-ai/how-i-improved-my-score-on-kaggles-june-2021-tabular-competition-by-using-bab6bbd0d803](https://medium.com/mlearning-ai/how-i-improved-my-score-on-kaggles-june-2021-tabular-competition-by-using-bab6bbd0d803)
  * [https://towardsdatascience.com/the-10-best-new-features-in-scikit-learn-0-24-f45e49b6741b](https://towardsdatascience.com/the-10-best-new-features-in-scikit-learn-0-24-f45e49b6741b)
  * [https://towardsdatascience.com/new-features-in-scikit-learn-f0ceb7e9d2ad](https://towardsdatascience.com/new-features-in-scikit-learn-f0ceb7e9d2ad)
  * [https://www.kaggle.com/carlmcbrideellis/histogram-gradient-boosting-regression-example](https://www.kaggle.com/carlmcbrideellis/histogram-gradient-boosting-regression-example)
  * [https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.HistGradientBoostingRegressor.html](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.HistGradientBoostingRegressor.html)
  * [https://machinelearningmastery.com/histogram-based-gradient-boosting-ensembles/](https://machinelearningmastery.com/histogram-based-gradient-boosting-ensembles/)

### 8) PoissonRegressor

Pros:
- The Poisson model is estimated by the maximum likelihood method, the estimates are adapted to the actual data. 
- It generally gives a better estimate of the counts for each record
- The Poisson model has a minimum value of 0. It will not predict negative values. This makes it
ideal for a distribution in which the mean or the most typical value is close to 0.
- This model is appropriate for counts of rare events, such as crime incidents
- Poisson models with robust standard errors are increasingly being recommended for situations in which it makes conceptual sense to model the log mean of the outcome

Cons:
- It makes strong assumptions regarding the distribution of the underlying data
- You'd get a loss of efficiency from using a Poisson regression compared to something more appropriate.
- A Poisson distribution would allow for nonzero probability only
- It can produce out-of-range predictions.
- Poisson regression assumes that the mean and variance are the same

Reference links:
  * [https://medium.com/@kn12/poisson-regression-implementation-python-28d15e95dc15](https://medium.com/@kn12/poisson-regression-implementation-python-28d15e95dc15)
  * [https://timeseriesreasoning.com/contents/poisson-regression-model/](https://timeseriesreasoning.com/contents/poisson-regression-model/)
  * [https://www.kaggle.com/gauravduttakiit/explore-the-poisson-regression](https://www.kaggle.com/gauravduttakiit/explore-the-poisson-regression)
  * [https://ml.dask.org/modules/generated/dask_ml.linear_model.PoissonRegression.html](https://ml.dask.org/modules/generated/dask_ml.linear_model.PoissonRegression.html)
  * [https://www.statisticshowto.com/poisson-regression/](https://www.statisticshowto.com/poisson-regression/)

### 9) LGBMRegressor 

Pros:
- Faster training speed and higher efficiency: Light GBM use histogram based algorithm i.e it buckets continuous feature values into discrete bins which fasten the training procedure.
- Lower memory usage: Replaces continuous values to discrete bins which result in lower memory usage.
- Better accuracy than any other boosting algorithm: It produces much more complex trees by following leaf wise split approach rather than a level-wise approach which is the main factor in achieving higher accuracy. However, it can sometimes lead to overfitting which can be avoided by setting the max_depth parameter.
- Compatibility with Large Datasets: It is capable of performing equally good with large datasets with a significant reduction in training time as compared to XGBOOST.
- Parallel learning supported.
- more accurate and time-saving

Cons:
- Narrow user base and less documentation availability
- It is not advisable to use LGBM on small datasets
- It is sensitive to overfitting and can easily overfit small data
- There is no threshold on the number of rows
- Need to use tuning to avoid overfitting, or speeding up the task and to achieve good accuracy.

Reference links:
  * [https://machinelearningmastery.com/light-gradient-boosted-machine-lightgbm-ensemble/](https://machinelearningmastery.com/light-gradient-boosted-machine-lightgbm-ensemble/)
  * [https://www.programcreek.com/python/example/88794/lightgbm.LGBMRegressor](https://www.programcreek.com/python/example/88794/lightgbm.LGBMRegressor)
  * [https://lightgbm.readthedocs.io/en/latest/pythonapi/lightgbm.LGBMRegressor.html](https://lightgbm.readthedocs.io/en/latest/pythonapi/lightgbm.LGBMRegressor.html)
  * [https://medium.com/@pushkarmandot/https-medium-com-pushkarmandot-what-is-lightgbm-how-to-implement-it-how-to-fine-tune-the-parameters-60347819b7fc](https://medium.com/@pushkarmandot/https-medium-com-pushkarmandot-what-is-lightgbm-how-to-implement-it-how-to-fine-tune-the-parameters-60347819b7fc)
  * [https://medium.com/analytics-vidhya/lightgbm-for-regression-with-categorical-data-b08eaff501d1](https://medium.com/analytics-vidhya/lightgbm-for-regression-with-categorical-data-b08eaff501d1)

### 10) Decision Tree Regression 
			   
Pros:
- The decision tree model can be used for both classification and regression problems, and it is easy to interpret, understand, and visualize. 
- The output of a decision tree can also be easily understood. 
- Compared with other algorithms, data preparation during pre-processing in a decision tree requires less effort and does not require normalization of data. 
- The implementation can also be done without scaling the data. 
- A decision tree is one of the quickest ways to identify relationships between variables and the most significant variable. 

Cons:
- Overfitting is one of the practical difficulties for decision tree models. It happens when the learning algorithm continues developing hypotheses that reduce the training set error but at the cost of increasing test set error. But this issue can be resolved by pruning and setting constraints on the model parameters. 
- Decision trees cannot be used well with continuous numerical variables. 
- A small change in the data tends to cause a big difference in the tree structure, which causes instability. 
- Calculations involved can also become complex compared to other algorithms, and it takes a longer time to train the model. 
- It is also relatively expensive as the amount of time taken and the complexity levels are greater.

Reference links:
  * [https://www.upgrad.com/blog/pros-and-cons-of-decision-tree-regression-in-machine-learning/](https://www.upgrad.com/blog/pros-and-cons-of-decision-tree-regression-in-machine-learning/)


### 11) LinearRegression 

Pros:
- Simple model : 
The Linear regression model is the simplest equation using which the relationship between the multiple predictor variables and predicted variable can be expressed.
- Computationally efficient : 
The modeling speed of Linear regression is fast as it does not require complicated calculations and runs predictions fast when the amount of data is large.
- Interpretability of the Output: 
The ability of Linear regression to determine the relative influence of one or more predictor variables to the predicted value when the predictors are independent of each other is one of the key reasons of the popularity of Linear regression. The model derived using this method can express the what change in the predictor variable causes what change in the predicted or target variable.

Cons :
- Overly-Simplistic:
The Linear regression model is too simplistic to capture real world complexity
- Linearity Assumption:
Linear regression makes strong assumptions that there is Predictor (independent) and Predicted (dependent) variables are linearly related which may not be the case.
- Severely affected by Outliers:
Outliers can have a large effect on the output, as the Best Fit Line tries to minimize the MSE for the outlier points as well, resulting in a model that is not able to capture the information in the data.
- Independence of variables :
Assumes that the predictor variables are not correlated which is rarely true. It is important to, therefore, remove multicollinearity (using dimensionality reduction techniques) because the technique assumes that there is no relationship among independent variables. In cases of high multicollinearity, two features that have high correlation will influence each other's weight and result in an unreliable model.
- Assumes Homoskedacity :
Linear regression looks at a relationship between the mean of the predictor/dependent variable and the predicted/independent variables and assumes constant variance around the mean which is unrealistic in most cases.
- Inability to determine Feature importance :
As discussed in the "Assumes independent variables" point, in cases of high multicollinearity, 2 features that have high correlation will affect each other's weight. 
If we run stochastic linear regression multiple times, the result may be different weights each time for these 2 features. So, it's we cannot really interpret the importance of these features.

Reference links:
  * [https://medium.com/@satyavishnumolakala/linear-regression-pros-cons-62085314aef0](https://medium.com/@satyavishnumolakala/linear-regression-pros-cons-62085314aef0)

### 12) LARS 
			   
Pros:
- Computationally as fast as forward selection but may sometimes be more accurate.
- Numerically very efficient when the number of features is much larger than the number of data instances.
- It can easily be modified to produce solutions for other estimators.
- If two variables are almost equally correlated with the response, then their coefficients should increase at approximately the same rate. The algorithm thus behaves as intuition would expect, and also is more stable.
- It produces a full piecewise linear solution path, which is useful in cross-validation or similar attempts to tune the model.

Cons:
- LARS is highly sensitive to noise and can produce unpredictable results sometimes.
- Because LARS is based upon an iterative refitting of the residuals, it would appear to be especially sensitive to the effects of noise. This problem is discussed in detail by Weisberg in the discussion section of the Efron et al. (2004) Annals of Statistics article.
- Lack of long-term studies and mixed results on the current base of knowledge.
- Residual post-operative laxity still present
- Requires tissue remnants of the ACL to be used in reconstruction

Reference links:
  * [https://venali.medium.com/conventional-guide-to-supervised-learning-with-scikit-learn-least-angle-regression-generalized-11b4ce2dec89](https://venali.medium.com/conventional-guide-to-supervised-learning-with-scikit-learn-least-angle-regression-generalized-11b4ce2dec89)
  * [https://www.physio-pedia.com/Ligament_Augmentation_and_Reconstruction_System_(LARS)](https://www.physio-pedia.com/Ligament_Augmentation_and_Reconstruction_System_(LARS))

### 13) SGD 
			   
Pros:
- In stochastic Gradient descent (SGD),s-and-cons-of-stochastic-gradient-descent-versus-Adam-as-optimisation-algorithms-used-in-Keras-machine-learning
   			   
Pros:
- In stochastic Gradient descent (SGD), we update the weights based on each training example, not the batch as a whole as done in GD.
- It is easier to fit in the memory due to a single training example being processed by the network.
- It is computationally fast as only one sample is processed at a time.
- For larger datasets, it can converge faster as it causes updates to the parameters more frequently.
- Due to frequent updates, the steps taken towards the minima of the loss function have oscillations that can help to get out of the local minimums of the loss function (in case the computed position turns out to be the local minimum).

Cons:
- Although SGD minimizes loss faster, it is noisier and it oscillates around the the minimum giving some variation in accuracy and loss run to run.
- Due to frequent updates, the steps taken towards the minima are very noisy. This can often lean the gradient descent into other directions.
- Also, due to noisy steps, it may take longer to achieve convergence to the minima of the loss function.
- Frequent updates are computationally expensive because of using all resources for processing one training sample at a time.
- It loses the advantage of vectorized operations as it deals with only a single example at a time.

Reference links:
  * [https://www.quora.com/What-are-the-pros-and-cons-of-stochastic-gradient-descent-versus-Adam-as-optimisation-algorithms-used-in-Keras-machine-learning](https://www.quora.com/What-are-the-pros-and-cons-of-stochastic-gradient-descent-versus-Adam-as-optimisation-algorithms-used-in-Keras-machine-learning)


### 14) Lasso Regression 

Pros: 
- As any regularization method, it can avoid overfitting. It can be applied even when number of features is larger than number of data.
- It can do feature selection.
- It is fast in terms of inference and fitting.
- Avoids over fitting
- Select features, by shrinking co-efficient towards zero.

Cons:
- The model selected by lasso is not stable. For example, on different bootstrapped data, the feature selected can be very different.
- The model selection result is not intuitive to interpret: for example, why lasso select a feature?
- When there are highly correlated features, lasso may randomly select one of them of part of them. The result depends on the implementation. To improve, people introduced elastic net.
- Based on my experience, its prediction performance is usually worse than ridge regression in terms of mse.
- Prediction performance is worse than Ridge regression.

Reference links:
  * [https://www.quora.com/What-are-the-pros-and-cons-of-lasso-regression](https://www.quora.com/What-are-the-pros-and-cons-of-lasso-regression)

### 15) ExtraTreesRegressor 

PROS:
- It reduces the variance of the model to a great extent.
- The execution time is faster.
- It adds randomisation but still has optimization.
- There is no repetition of data.
- Has high performance with noisy features.

CONS:
- There is a greater increase in bias.
- It randomly chooses the split point and not the optimal one.
- It involves higher number of iterations.

Reference links:
* [https://scikit-learn.org/stable/modules/ensemble.html#forest](https://scikit-learn.org/stable/modules/ensemble.html#forest)
* [https://scikit-learn.org/stable/modules/ensemble.html#forest](https://scikit-learn.org/stable/modules/ensemble.html#forest)
* [https://stats.stackexchange.com/questions/175523/difference-between-random-forest-and-extremely-randomized-trees](https://stats.stackexchange.com/questions/175523/difference-between-random-forest-and-extremely-randomized-trees)
* [https://www.kaggle.com/hkapoor/random-forest-vs-extra-trees] (https://www.kaggle.com/hkapoor/random-forest-vs-extra-trees)

### 16) Kernel Ridge 

PROS:
- There exists formulas to computer the leave-one-out mean-squared error.
- It handles the problem of overfitting.
- It works really well with datasets having large number of features than training samples.
- It improves the least square estimate.
- The computational effiency for lower dimensional data is high.
- It maintains the magnitude of the coefficient as small as possible.


CONS:
- It uses all the input features in the dataset, unlike step-wise methods that only select a few important features for regression.
- It reduces the coefficients theta to very low values if the feature is not important, but it won't completely make them zero.
- The output is not unbiased.
- It is not the best option for collinear data.
- Bias-variance tradeoff must be used if regularisation is performed.

Reference links:
* [http://clopinet.com/isabelle/Projects/ETH/KernelRidge.pdf](http://clopinet.com/isabelle/Projects/ETH/KernelRidge.pdf)
* [https://iq.opengenus.org/ridge-regression/](https://iq.opengenus.org/ridge-regression/)
* [https://www.quora.com/What-are-the-advantages-and-disadvantages-of-using-regularization-methods-like-Ridge-regression](https://www.quora.com/What-are-the-advantages-and-disadvantages-of-using-regularization-methods-like-Ridge-regression)

