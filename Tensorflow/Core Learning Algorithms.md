[core algorithms](https://colab.research.google.com/drive/1YaRbNpePrErZ1t6PHbDk0pxuE0ipYcKP)
#### Linear Regression

Example: Titanic problem
1.  ***Feature Columns***
In our dataset we have two different kinds of information: **Categorical and Numeric**

Our **categorical data** is anything that is not numeric! For example, the sex column does not use numbers, it uses the words "male" and "female".

Before we continue and create/train a model we must convet our categorical data into numeric data. We can do this by encoding each category with an integer (ex. male = 1, female = 2).
```python
CATEGORICAL_COLUMNS = ['sex', 'n_siblings_spouses', 'parch', 'class', 'deck', 'embark_town', 'alone']
NUMERIC_COLUMNS = ['age', 'fare']
feature_columns = []

for feature_name in CATEGORICAL_COLUMNS:
  vocabulary = dftrain[feature_name].unique()  # gets a list of all unique values from given feature column
feature_columns.append(tf.feature_column.categorical_column_with_vocabulary_list(feature_name, vocabulary))

for feature_name in NUMERIC_COLUMNS:
	feature_columns.append(tf.feature_column.numeric_column(feature_name, dtype=tf.float32))

print(feature_columns)
```

2. ***linearClassifier***
```python
linear_est = tf.estimator.LinearClassifier(feature_columns=feature_columns)

# We create a linear estimtor by passing the feature columns we created earlier
```

3. ***Train the model***
```python
linear_est.train(train_input_fn)  # train
result = linear_est.evaluate(eval_input_fn)  # get model metrics/stats by testing on tetsing data
clear_output()  # clears consoke output
print(result['accuracy'])  # the result variable is simply a dict of stats about our model
print(result)
```
### Classification
**Keras**: Sub model of Tensorflow

### Clustering


### Hidden Markow Models