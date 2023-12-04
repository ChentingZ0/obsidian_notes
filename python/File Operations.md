```python
import pandas as pd
inputfile = 'wiki-1.csv'
separator = '#'

with open(inputfile) as fp:
    line = fp.readline()
    while line:
        lineSplit = str.split(line, separator)
        u = lineSplit[0].rstrip()
        v = lineSplit[1].rstrip()
        print(line)
        line = fp.readline()
```
