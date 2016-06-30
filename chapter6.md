---
title       : Expert advice to improve model performance
description : This chapter will help to understand the approach of data science experts, "How they do approach a challenge ?", "How to select a right algorithm ?", "How to combine outputs of multiple algorithms ?" and "How to select the right value of model parameter also known as parameter tuning ?".

--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:9a8fd577a9
## How to approach a challenge?

The model development cycle goes through various stages, starting from data collection to model building. Most of us admit that data exploration needs more attention to unleashing the hidden story of data but before exploring the data to understand relationships (in variables), It’s always recommended to perform hypothesis generation. (To know more  about hypothesis generation, refer to <a href =" http://discuss.analyticsvidhya.com/t/why-and-when-is-hypothesis-generation-important/2109"> this link</a>). 

It is important that you spend time thinking about the given problem and gaining the domain knowledge. So, how does it help?

This practice usually helps in building better features later on, which are not biased by the data available in the dataset. This is a crucial step which usually improves a model’s accuracy.

At this stage, you are expected to apply structured thinking to the problem i.e. a thinking process which takes into consideration all the possible aspects of a particular problem.


####Which of the following has the right order of model building life cycle?


*** =instructions
- Data Collection --> Data Exploration --> Hypothesis Generation --> Model Building --> Prediction
- Data Collection --> Hypothesis Generation --> Data Exploration --> Model Building --> Prediction
- Hypothesis Generation --> Data Collection --> Data Exploration --> Model Building --> Prediction

*** =hint
Always perform hypothesis generation before data collection and exploration, it also helps you to collect right data

*** =pre_exercise_code


*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package

msg_bad1 = "Think again!"
msg_success = "Exactly! we always do Hypothesis generation before data collection and exploration"

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(3, [msg_bad1, msg_bad1, msg_success]) 
```

--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:01167ddb1f
## Feature Engineering

This step helps to extract more information from existing data. New information is extracted in terms of new features. These features may have a higher ability to explain the variance in the training data. Thus, giving improved model accuracy.

Feature engineering is highly influenced by hypotheses generation. A good hypothesis results in a good feature. That’s why experts always suggest investing quality time in hypothesis generation. Feature engineering process can be divided into two steps:

* Feature Transformation
* Feature Creation

##### Feature Transformation: 

There are various scenarios where feature transformation is required:
* Changing the scale of a variable from original scale to scale between zero and one.
* Some algorithms works well with normally distributed data. Therefore, we must remove skewness of variable(s). There are methods like log, square root or inverse of the values to remove skewness
* Binning of numerical variables

##### Feature Creation: 

Deriving new variable(s) from existing variables is known as feature creation. It helps to unleash the hidden relationship of a data set. Let’s say, we want to predict the number of transactions in a store based on transaction dates. Here transaction dates may not have a direct correlation with the number of transaction, but if we look at the day of a week, it may have a higher correlation. In this case, the information about the day of the week is hidden. We need to extract it to make the model better.

#### Creating a variable based on a mathematical computation on three existing variables is a method of?


*** =instructions
- Feature Transformation
- Feature Creation
- Feature Selection


*** =hint
Creating a new variable from existing data set is known as feature creation

*** =pre_exercise_code


*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package

msg_bad1 = "Think again!"
msg_success = "Yes! Creating a new feature out of existing ones is known as feature creation"

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(2, [msg_bad1, msg_success, msg_bad1]) 
```

--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:3c72c926e8
## Feature Selection

Feature Selection is a process of finding out the best subset of attributes which better explains the relationship of independent variables with target variable.

You can select the useful features based on various metrics like:

* Domain Knowledge: Based on domain experience, we select feature(s) which may have a higher impact on target variable.
* Visualization: As the name suggests, it helps to visualize the relationship between variables, which makes your variable selection process easier.
* Statistical Parameters: We also consider the p-values, information values, and other statistical metrics to select right features.

#### Variable importance table of random forest classifier can act as feature selection tool?


*** =instructions
- TRUE
- FALSE


*** =hint
Variable importance table shows the importance of each variable with respect to target variable

*** =pre_exercise_code


*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package

msg_bad1 = "Think again!"
msg_success = "Yes! Creating a new feature out of existing ones is known as feature creation"

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(1, [msg_success, msg_bad1]) 
```

--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:a93345ad36
## How to select the right value of model parameter?

We know that machine learning algorithms are driven by parameters. These parameters majorly influence the outcome of the learning process.

The objective of parameter tuning is to find the optimum value for each parameter to improve the accuracy of the model. To tune these parameters, you must have a good understanding of their meaning and individual impact on the model. You can repeat this process with a number of well-performing models.

For example: In a random forest, we have various parameters like max_features, number_trees, random_state, oob_score and others. Intuitive optimization of these parameter values will result in better and more accurate models.

#### Which of the following is not a parameter of random forest algorithm (in Scikit Learn)?


*** =instructions
- max_depth
- max_leaf_node
- learning rate
- max_features


*** =hint
List of all parameters in random forest scikit learn algorithm:

RandomForestClassifier(n_estimators=10, criterion='gini', max_depth=None,min_samples_split=2, min_samples_leaf=1, min_weight_fraction_leaf=0.0, max_features='auto', max_leaf_nodes=None,bootstrap=True, oob_score=False, n_jobs=1, random_state=None, verbose=0, warm_start=False,class_weight=None)

*** =pre_exercise_code


*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package

msg_bad1 = "Look at the hint to know more about parameters of random forest"
msg_success = "Good Job!"

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(3, [msg_bad1, msg_bad1, msg_success, msg_bad1]) 
```

--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:63b7c07abc
## Use ensemble methods to combine output of more than one models?

This is the most common approach found majorly in winning solutions of Data science competitions. This technique simply combines the result of multiple weak models and produce better results. This can be achieved through many ways:

* Bagging (Bootstrap Aggregating)
* Boosting

To know more about these methods, you can refer article <a href="http://www.analyticsvidhya.com/blog/2015/08/introduction-ensemble-learning/"> “Introduction to ensemble learning“ </a>.

It is always a better idea to apply ensemble methods to improve the accuracy of your model. There are two good reasons for this: 
* They are generally more complex than traditional methods 
* The traditional methods give you a good base level from which you can improve and draw from to create your ensembles.

#### Taking the average of predictions (given by different models) is an example of ensemble model?


*** =instructions
- TRUE
- FALSE

*** =hint
We can combine output of different base models by:
- Taking average of all predictions
- Using maximum vote techniques


*** =pre_exercise_code


*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package

msg_bad1 = "Read more about ensemble methods"
msg_success = "Good Job!"

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(1, [msg_success, msg_bad1]) 
```

--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:60de1e0b02
## Cross validtion helps to improve your score on out of sample data set

Till here, we have seen methods which can improve the accuracy of a model. But, it is not necessary that higher accuracy models always perform better (for unseen data points). Sometimes, the improvement in model’s accuracy can be due to over-fitting too.

Here Cross-Validation helps to find the right answer to this question. Cross Validation says, try to leave a sample on which you do not train the model and test the model on this sample before finalizing the model. This method helps us to achieve more generalized relationships. To know more about this cross validation method, you should refer article <a href="http://www.analyticsvidhya.com/blog/2015/11/improve-model-performance-cross-validation-in-python-r/"> “Improve model performance using cross-validation“ </a>.

#### Common methods used for Cross-Validation ?


##### The Validation set Approach:
In this approach, we reserve 50% of the dataset for validation and rest 50% for model training. A major disadvantage of this approach is that we train a model on 50% of the dataset only, it may be possible that we are leaving some interesting information about data i.e. higher bias.

##### Leave one out cross validation (LOOCV)

In this approach, we reserve only one data-point of the available data set. And, train model on the rest of data set. This process iterates for each data point. This approach leads to higher variation in testing model effectiveness because we test against one data point. So, our estimation gets highly influenced by that one data point. If the data point turns out to be an outlier, it can lead to higher variation.

##### K-fold cross validation

In this method, we follow below steps:
* Randomly split your entire dataset into k-”folds”.
* For each k folds in your dataset, build your model on k – 1 folds of the data set. 
* Then, test the model to check the effectiveness for kth fold and record the error you see on each of the predictions.
* Repeat this until each of the k folds has served as the test set.

The average of your k recorded errors is called the cross-validation error and will serve as your performance metric for the model.

#### How to choose right value of k for K-fold cross validation?

*** =instructions
- Choose lower value of K
- Choose a higher value of K
- Use k=10

*** =hint
Always remember, lower value of K is more biased and hence undesirable. On the other hand, a higher value of K is less biased; but it can suffer from large variability. It is good to know that a smaller value of k always takes us towards validation set approach, whereas the higher value of k leads to LOOCV approach. Hence, it is often suggested to use k=10.

*** =pre_exercise_code


*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package

msg_bad1 = "Try again! Read more about Cross Validation"
msg_success = "Good Job!"

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(3, [msg_bad1, msg_bad1, msg_success]) 
```

--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:ed0dcad240
## iPython / Jupyter notebook for Predictive Modeling

The Jupyter Notebook is a web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text. Uses include: data cleaning and transformation, numerical simulation, statistical modeling, machine learning and much more.

We have shared the Jupyter notebook for your reference here

### Download the jupyter notebook from <a href = "https://nbviewer.jupyter.org/github/kunalj101/python_intro_hackathon/blob/master/DataCamp_Model_Building.ipynb">here</a>. Have you downloaded the jupyter notebook?



*** =instructions
- Yes, I have downloaded the file
- No, I am not able to


*** =hint
Click on the link and download the Jupyter notebook. 

*** =pre_exercise_code


*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package

msg1 = "Awesome! You can proceed to model building now!"
msg2 = "Check the link provided and download the file from there."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(1,, [msg1, msg2]) 
```
--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:ed0dcad240
## Thank You & Further studies

Thanks for taking up this open course from <a href="http://www.analyticsvidhya.com">Analytics Vidhya </a>. We hope you enjoyed the problem solving exercises and our hackathon experience. For more such hackathons, you can always visit our <a href="http://datahack.analyticsvidhya.com"> DataHack platform.</a>

###Here are a few more resources you can check out:

####Practice Problems (Hackathons):
- <a href="http://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii">Big Mart Sales Problem</a>.

####All Hackathons:
- <a href="http://datahack.analyticsvidhya.com/contest/all">All Hackathons</a>.

####Tutorials
- <a href="http://www.analyticsvidhya.com/learning-paths-data-science-business-analytics-business-intelligence-big-data/learning-path-data-science-python/" >Learning path in Python - Path from beginner to an expert in Data Science</a>
- <a href = "http://www.analyticsvidhya.com/learning-paths-data-science-business-analytics-business-intelligence-big-data/learning-path-r-data-science/">LeaRning path in R - Path from beginner to an expert in Data Science</a>
- <a href = "http://www.analyticsvidhya.com/blog/2015/08/common-machine-learning-algorithms/">Essentials of Machine Learning (with codes in Python & R)</a>
- <a href = "http://www.analyticsvidhya.com/blog/2016/01/12-pandas-techniques-python-data-manipulation/">12 useful Pandas techniques for Data Manipulation</a>
- <a href = "http://www.analyticsvidhya.com/blog/2016/02/time-series-forecasting-codes-python/">Complete guide to create a time series forecast (with codes in Python)</a>
 
####<a href="http://discuss.analyticsvidhya.com">Data Science Discussions</a>


*** =instructions
What do you want to do next:
- Finish the course
- Stay on this page and explore the references


*** =hint
Thank You - hope you enjoyed the course. 

*** =pre_exercise_code


*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package

msg1 = "Thanks for completing the course. Looking forward to interacting with you on DataHack."
msg2 = "No hurry! You can take your own time."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(1,, [msg1, msg2]) 
```
