[notebook](https://colab.research.google.com/drive/1Plk6f3l5ZGKW4CJFfJKP9hNUUOw7rw4_#scrollTo=duDj86TfWFof)
Tensorflow has two main components that we will try to understand
- **Graphs**
Tensorflow works by building a graph of defined computations.
Nothing is computed or stored in this graph. It is simply a way of defining the operations that have been written in code.

- **Sessions**
It allows part of the graph to be executed. It allocates memory and resources and handles the execution of the operations and computations we've defined.

### Tensor
It should't surprise you that tensors are a fundemental apsect of TensorFlow.

A tensor is a generalization of vectors and matrices to potentially higher dimensions. Internally, TensorFlow represents tensors as n-dimensional arrays of base datatypes.

They are the main objects that are passed around and manipulated throughout the program. Each tensor represents a **partially defined computation** that will eventually produce a value. TensorFlow programs work by building **a graph of Tensor objects** that details how tensors are related. Running different parts of the graph allow results to be generated.

Each tensor has a data type and a shape.
**Data Types Include**: float32, int32, string and others.
**Shape**: Represents the dimension of data.
Just like vectors and matrices tensors can have operations applied to them like addition, subtraction, dot product, cross product etc.

### Create Tensors
There are different types of tensors
- Variable
- Constant
- Placeholder
- SparseTensor
With the execption of `Variable` all these tensors are immuttable, meaning their value may not change during execution.

For now, it is enough to understand that we use the Variable tensor when we want to potentially change the value of our tenso
```python
# syntax = tf.Variable(value, datatype)
String = tf.Variable("This is a string", tf.string)
number = tf.Variable(324, tf.int16)
floating = tf.Variable(3.567, tf.float64)
```
**Rank/degree and shape**
- The rank of a tensor is direclty related to the deepest level of nested lists.
- The shape of a tensor is simply the number of elements that exist in each dimension

The number of dimensions involved in the tensor. What we created above is a _tensor of rank 0_, also known as a scalar.
```python
rank1_tensor = tf.Variable(["Test"], tf.string)
rank2_tensor = tf.Variable([["test", "ok"], ["test", "yes"]], tf.string)
tf.rank(rank2_tensor)
rank2_tensor.shape
```

