X and y should be np arrays (many functions require that and it's computationally optimized)

```python
y = df['label'].values # label is our target column
X = df.drop(columns=['label']).values # everything but our label
```

train and test split, default 0.8

```python
from sklearn.model_selection import train_test_split

train_X, val_X, train_y, val_y = train_test_split(X, y,random_state = 0)
```