```python
import torchvision.transforms.functional as tf
pic = Image.open(...)
tf.to_tensor(pic) → [Tensor]
```
Convert a `PIL Image` or `numpy.ndarray` to tensor.

