In PyTorch, the `gather` function is used to gather values from a source tensor based on the indices specified in another tensor.

Index tensor must have the same number of dimensions as input tensor
```python
import torch

# Create a values tensor
values = torch.tensor([[10, 20, 30],
                       [40, 50, 60]])

# Create an actions tensor with indices
actions = torch.tensor([1, 0])

# Gather values based on indices
result = values.gather(1, actions.view(-1, 1))

print(result)
```

![[Pasted image 20231218213826.png]]

