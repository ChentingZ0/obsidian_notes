- General example
```python
import argparse

# Create the parser  
parser = argparse.ArgumentParser()

# Add an argument  
parser.add_argument('--name', type=str, required=True)

# Parse the argument  
args = parser.parse_args()

# Print "Hello" + the user input argument  
print('Hello,', args.name)
```

![[Pasted image 20240116153336 1.png]]
![[Pasted image 20240116153350 1.png]]


- In Neural Network
```python
from argparse import ArgumentParser
parser = ArgumentParser(description="Training script parameters")  
parser.add_argument('--model_paths', '-m', required=True, nargs="+", type=str, default=[])  
args = parser.parse_args()  
evaluate(args.model_paths)
```
