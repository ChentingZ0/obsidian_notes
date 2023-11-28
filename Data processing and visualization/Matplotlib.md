- `plt.axvline` -> draw vertical lines
```python
ax = data_orig.plot(x='Date', y='Montreal_Median_Price', figsize=(12,6))
xcoords = ['2015-01-01', '2016-01-01','2017-01-01', '2018-01-01', '2019-01-01', '2020-01-01','2021-01-01']

for xc in xcoords:
	plt.axvline(x=xc, color='black', linestyle='--')|
```

```python
plt.grid()
# 加网格
```
![example](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*iIlqAAYmTuXHZ5mUsDUjHw.png)

- 创建图像文件+设置坐标
```python
# Create figure of the size of the maze  
fig = plt.figure(1, figsize=(cols,rows))  
  
# Remove the axis ticks and add title title  
ax = plt.gca()  
ax.set_title('Policy simulation')  
ax.set_xticks([])  
ax.set_yticks([])
```
The acronym `gca` stands for "get current axis". This function returns the current Axes instance on the current figure.

- 创建格子类文件
并给每一个格子上色 
```python
# Give a color to each cell  
# Some colours  
LIGHT_RED = '#FFC4CC'  
LIGHT_GREEN = '#95FD99'  
BLACK = '#000000'  
WHITE = '#FFFFFF'  
LIGHT_PURPLE = '#E8D0FF'  
LIGHT_ORANGE = '#FAE0C3'

col_map = {0: WHITE, 1: BLACK, 2: LIGHT_GREEN, -6: LIGHT_RED, -1: LIGHT_RED}

colored_maze = [[col_map[maze[j, i]] for i in range(cols)] for j in range(rows)]  
  
# Create figure of the size of the maze  
fig = plt.figure(1, figsize=(cols, rows))  
  
# Create a table to color  
grid = plt.table(cellText=None,  
cellColours=colored_maze,  
cellLoc='center',  
loc=(0, 0),  
edges='closed')  
  
# Modify the height and width of the cells in the table  
tc = grid.properties()['children']  
for cell in tc:  
cell.set_height(1.0/rows)  
cell.set_width(1.0/cols)
```

