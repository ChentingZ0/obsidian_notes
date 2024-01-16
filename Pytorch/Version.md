My cuda version: 12.1
Command
```python
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```

Check 
```python
import torch
torch.cuda.is_available()

x = torch.rand(5, 3)
print(x)
```

