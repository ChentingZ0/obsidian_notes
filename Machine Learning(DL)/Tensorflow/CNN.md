### **Convolutional Neural Network**
[notebook of youtube](https://colab.research.google.com/drive/18mvSuGdBMKKbNPil4Z_Vz-jBptan9Tw_#scrollTo=PuGu50NlgreO)
- Image classification
- Object detection

***Concepts***
It learns local patterns and find patterns in any part of the image while dense neural networks work on a global scale.

- Filters
- Feature Map
This term simply stands for a 3D tensor with two special axes (width and height) and one depth axis. Our convolutional layers take feature maps as their input and return a new feature map that represents the presence of specific filters from the previous feature map.
![feature map](https://drive.google.com/uc?export=view&id=1HcLvvLKvLCCGuGZPMvKYz437FbbCC2eB)
- Borders and Padding
![border and padding](https://drive.google.com/uc?export=view&id=1OEfXrV16NBjwAafgBfYYcWOyBCHqaZ5M)
- Strides 
- Pooling
The idea behind a pooling layer is to downsample our feature maps and reduce their dimensions. They work in a similar way to convolutional layers where they extract windows from the feature map and return a response map of the max, min or average values of each channel. Pooling is usually done using windows of size 2x2 and a stride of 2. This will reduce the size of the feature map by a factor of two and return a response map that is 2x smaller.

### Create a CNN by Tensorflow
- ***Model Architecture***
```python
model = models.Sequential()
model.add(layers.Conv2D(32, (3, 3), activation='relu', input_shape=(32, 32, 3)))
model.add(layers.MaxPooling2D((2, 2)))
model.add(layers.Conv2D(64, (3, 3), activation='relu'))
model.add(layers.MaxPooling2D((2, 2)))
model.add(layers.Conv2D(64, (3, 3), activation='relu'))

# Adding Dense Layers
model.add(layers.Flatten())
model.add(layers.Dense(64, activation='relu'))
model.add(layers.Dense(10))

model.summary()
```

- ***Training the model*** 
```python
model.compile(optimizer='adam', loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True),
              metrics=['accuracy'])
history = model.fit(train_images, train_labels, epochs=4,
                    validation_data=(test_images, test_labels))
```

- ***Evaluating the model***
```python
test_loss, test_acc = model.evaluate(test_images,  test_labels, verbose=2)
print(test_acc)
```


