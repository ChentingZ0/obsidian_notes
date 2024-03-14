```python
pip install tensorboard
tensorboard --logdir=runs
```
- `--logdir=runs`: Here, `--logdir` specifies the directory where TensorBoard will look for log files to display. In this case, it's set to look in the `runs` directory.

When you run this command, TensorBoard will start and read the log files located in the `runs` directory, which typically contain data from machine learning experiments, like training metrics. TensorBoard then provides a web interface for visualizing this data, such as loss and accuracy curves, model graph visualizations, and more.

