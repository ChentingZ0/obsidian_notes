- **Squeeze**
Returns a tensor with all specified dimensions of `input` of size 1 removed.
`torch.squeeze(_input_, _dim=None_)`
```python
torch.tensor([[1,2,3,4]])
x = x.squeeze(0)
Ans: tensor([1, 2, 3, 4]) 
```
For example, if input is of shape: (A×1×B×C×1×D) then the input.squeeze() will be of shape: (A×B×C×D).

- **Unsqueeze**
Returns a new tensor with a dimension of size one inserted at the specified position.
`torch.unsqueeze(_input_, _dim_) → [Tensor]`
Parameters

- **input** (Tensor) – the input tensor.
- **dim** (int) – the index at which to insert the singleton dimension
```python
x = torch.tensor([1, 2, 3, 4])
torch.unsqueeze(x, 0)
Ans: tensor([[ 1,  2,  3,  4]])

torch.unsqueeze(x, 1)
Ans: tensor([[ 1],
        [ 2],
        [ 3],
        [ 4]])
```


