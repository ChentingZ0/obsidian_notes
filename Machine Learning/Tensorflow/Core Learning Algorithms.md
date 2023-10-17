[core algorithms](https://colab.research.google.com/drive/1YaRbNpePrErZ1t6PHbDk0pxuE0ipYcKP)
#### Linear Regression
[Tensorflow tutorial](https://www.tensorflow.org/tutorials/estimator/linear)
Example: Titanic problem
1.  ***Feature Columns***
Feature engineering
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

2. ***Prepare the data***
The TensorFlow model we are going to use requires that the data we pass it comes in as a `tf.data.Dataset` object. This means we must create a _input function_ that can convert our current pandas dataframe into that object.
```python
def make_input_fn(data_df, label_df, num_epochs=10, shuffle=True, batch_size=32):
  def input_function(): 
    ds = tf.data.Dataset.from_tensor_slices((dict(data_df), label_df))  
    # create tf.data.Dataset object with data and its label
    if shuffle:
      ds = ds.shuffle(1000)  # randomize order of data
    ds = ds.batch(batch_size).repeat(num_epochs)  
    # split dataset into batches of 32 and repeat process for number of epochs
    return ds  # return a batch of the dataset
  return input_function  # return a function object for use

  
train_input_fn = make_input_fn(dftrain, y_train)  # here we will call the input_function that was returned to us to get a dataset object we can feed to the model
eval_input_fn = make_input_fn(dfeval, y_eval, num_epochs=1, shuffle=False)
```

3. ***create the model***
```python
linear_est = tf.estimator.LinearClassifier(feature_columns=feature_columns)

# We create a linear estimtor by passing the feature columns we created earlier
```

4. ***Train the model***
```python
linear_est.train(train_input_fn)  # train
result = linear_est.evaluate(eval_input_fn)  # get model metrics/stats by testing on tetsing data
clear_output()  # clears consoke output
print(result['accuracy'])  # the result variable is simply a dict of stats about our model
print(result)

# prediction
result = list(linear_est.predict(eval_input_fn))
print(result[0]['probabilities'][1])
```
### Classification
1. Create tf.data.Dataset (similar)
2. Create the feature columns (similar)
3. ***Build the model***

 For classification tasks there are variety of different estimators/models that we can pick from. Some options are listed below.(premade models)
- `DNNClassifier` (Deep Neural Network)
- `LinearClassifier`

```python
# Build a DNN with 2 hidden layers with 30 and 10 hidden nodes each.
# A simple example
classifier = tf.estimator.DNNClassifier(
    feature_columns=my_feature_columns,
    # Two hidden layers of 30 and 10 nodes respectively.
    hidden_units=[30, 10],
    # The model must choose between 3 classes.
    n_classes=3)
```

4. ***train and evaluate*** the model
classifier.train(...)
classifier.predict(...)
```python
classifier.train(
    input_fn=lambda: input_fn(train, train_y, training=True),
    steps=5000)

eval_result = classifier.evaluate(
    input_fn=lambda: input_fn(test, test_y, training=False))

print('\nTest set accuracy: {accuracy:0.3f}\n'.format(**eval_result))
```

5. ***Prediction***
classifier.predict(...)
```python
def input_fn(features, batch_size=256):
    # Convert the inputs to a Dataset without labels.
    return tf.data.Dataset.from_tensor_slices(dict(features)).batch(batch_size)

  
features = ['SepalLength', 'SepalWidth', 'PetalLength', 'PetalWidth']
predict = {}

print("Please type numeric values as prompted.")
for feature in features:
  valid = True
  while valid:
    val = input(feature + ": ")
    if not val.isdigit(): valid = False
  predict[feature] = [float(val)]

  
predictions = classifier.predict(input_fn=lambda: input_fn(predict))
for pred_dict in predictions:
    class_id = pred_dict['class_ids'][0]
    probability = pred_dict['probabilities'][class_id]
    print('Prediction is "{}" ({:.1f}%)'.format(
        SPECIES[class_id], 100 * probability))
```
### Clustering
[5 clustering algorithms](https://towardsdatascience.com/the-5-clustering-algorithms-data-scientists-need-to-know-a36d136ef68)

### Hidden Markow Models
- States
- Transition Distribution
- Observation Distribution
[Tensorflow tutorial](https://www.tensorflow.org/probability/api_docs/python/tfp/distributions/HiddenMarkovModel)

```python
import tensorflow_probability as tfp  
# We are using a different module from tensorflow this time
import tensorflow as tf
```
