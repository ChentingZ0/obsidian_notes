#### duration time
```python
import time
start = time.time()
n = 40
fib = fibonacci(n)
end = time.time()
print(f'Computing it took {end-start} seconds')

# time.sleep: specifies the duration of the pause.
time.sleep(0.05)
```

#### ipdb
python debugger tool
```python
import ipdb
...
ipdb.set_trace()
...
```
`ipdb> s` means going to the next line