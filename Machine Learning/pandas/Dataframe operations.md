```python
df = pd.read_csv("/path")
df.head()
y_train = dftrain.pop("survived")
df["age"]   # for all the information in that column
df.loc[0]   # for all the information of the first row
df.describe()
df.shape
df.age.hist(bins=..)
df.sex.value_counts().plot(kind='...')
df['class'].value_counts().plot(kind='...')
pd.concat([df1, df2]).groupby('sex')
df['sex'].unique()

```