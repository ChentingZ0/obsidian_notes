## **Dense Neural Networks**
***Keras***: Sub model of Tensorflow

***Concepts***:
[Terminology](https://colab.research.google.com/drive/1tHCOsxKLrxI0Mz5eYYo61zeuBpvIp-Xv#scrollTo=Q2xNjpctlBUM)
- Weights
- Bias
- Activation function(Relu, softmax, etc)
$Y =F((\sum_{i=0}^n w_i x_i) + b)$

- Input Layer
- Output Layer
- Hidden Layers
- Neurons
- Connected Layers(Dense layer)

- Backpropagation
- Loss function(Mean Square Error, Hinge Loss, etc)
- Optimizer(Gradient Descent, Stochastic Gradient Descent, Mini-batch GD, etc)
![gradient descent](https://cdn-images-1.medium.com/max/1000/1*iU1QCnSTKrDjIPjSAENLuQ.png)

### Create a Dense Neural Network by Tensorflow(Example)
[example](https://colab.research.google.com/drive/1tHCOsxKLrxI0Mz5eYYo61zeuBpvIp-Xv#scrollTo=wHde8MYW0OQo)
1. ***Data Preprocessing***
Load the dataset
```python
import tensorflow as tf
from tensorflow import keras
import numpy as np
import matplotlib.pyplot as plt

fashion_mnist = keras.datasets.fashion_mnist  # load dataset
(train_images, train_labels), (test_images, test_labels) = fashion_mnist.load_data()
```

Most important part, reshape and make sure it fit into the model
Mapping the pixel data from (0-255) to (0-1)
```python
train_images = train_images / 255.0
test_images = test_images / 255.0
```

2. ***Build the model***
Use tools like tensorflow and keras
```python
model = keras.Sequential([
    keras.layers.Flatten(input_shape=(28, 28)),  # input layer (1)
    keras.layers.Dense(128, activation='relu'),  # hidden layer (2)
    keras.layers.Dense(10, activation='softmax') # output layer (3)
])
```

Note: 
For the output layer: Each neuron represents the probabillity of a given image being one of the 10 different classes. The activation function _softmax_ is used on this layer to calculate a probabillity distribution for each class. This means the value of any neuron in this layer will be between 0 and 1, where 1 represents a high probabillity of the image being that class.

3. ***Compile the model***
```python
# Hyper parameter tuning 
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])
```

4. ***Training the model***
```python
model.fit(train_images, train_labels, epochs=10) 
```

5. ***Evaluating the model***
```python
test_loss, test_acc = model.evaluate(test_images,  test_labels, verbose=1)
print('Test accuracy:', test_acc)
```
The accuracy in test dataset is lower than when training the model. This difference is reffered to as **overfitting**.

6. ***Making Predictions***
```python
predictions = model.predict(test_images)
np.argmax(predictions[0])
test_labels[0]
```