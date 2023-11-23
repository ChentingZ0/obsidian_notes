- `plt.axvline` -> draw vertical lines
```python
ax = data_orig.plot(x='Date', y='Montreal_Median_Price', figsize=(12,6))
xcoords = ['2015-01-01', '2016-01-01','2017-01-01', '2018-01-01', '2019-01-01', '2020-01-01','2021-01-01']

for xc in xcoords:
	plt.axvline(x=xc, color='black', linestyle='--')|
```

![example](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*iIlqAAYmTuXHZ5mUsDUjHw.png)
