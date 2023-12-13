# Examples of usage: `.groupby()`

### Grouping and sum calculation
```python
df.groupby('Category').sum()
```
Group by 'Category' and sum all numeric columns.

### Grouping and Mean Calculation:

```python
df.groupby('Department')['Salary'].mean()
```
Group by 'Department' and calculate the mean of 'Salary'.

### Grouping by Multiple Columns
```python
df.groupby(['Region', 'Department']).mean()
```
Group by 'Region' and 'Department', and calculate mean of all numeric columns.

### Grouping and Counting Unique Values

```python
df.groupby('Department')['EmployeeID'].nunique()
```
Group by 'Department' and count unique 'EmployeeID' values.

### Grouping with Aggregation

```python
df.groupby('Category').agg({'Price': 'mean', 'Quantity': 'sum'})
```
Group by 'Category', then calculate mean of 'Price' and sum of 'Quantity'.

### Grouping and Size

```python
df.groupby('Category').size()
```
Group by 'Category' and get the size of each group.

### Grouping and Descriptive Statistics

```python
df.groupby('Category')['Price'].describe()
```
Group by 'Category' and get descriptive statistics for 'Price'.

### Grouping with Custom Function

```python
df.groupby('Department')['Salary'].apply(lambda x: x.max() - x.min())
```

Group by 'Department' and calculate the salary range (max - min) in each department.

### Grouping by Date Components

```python

df.groupby(df['Date'].dt.year)['Sales'].sum()
```
Group by year of 'Date' and sum 'Sales'.

### Grouping and Filtering

```python
df.groupby('Category').filter(lambda x: x['Price'].mean() > 20)
```

Filter groups in 'Category' where average 'Price' is greater than 20.

### Grouping with Sorting

```python
df.groupby('Category')['Price'].mean().sort_values(ascending=False)
```

Group by 'Category', calculate the mean 'Price', and sort the results in descending order.

### Grouping and Getting the First Entry

```python
df.groupby('Department').first()
```
Group by 'Department' and return the first row of each group.

### Grouping and Sampling

```python
df.groupby('Category').apply(lambda x: x.sample(n=1))
```

Group by 'Category' and randomly sample one row from each group.

### Nested Grouping

```python
df.groupby(['Region', 'Department'])['Sales'].sum()
```

Group by both 'Region' and 'Department', then sum 'Sales'.

### Grouping by Index

```python
df.groupby(df.index.month)['Revenue'].sum()
```

Group by the month of the index (assuming it's a datetime index) and sum 'Revenue'.

### Cumulative Sum within Groups

```python
df.groupby('Category')['Sales'].cumsum()
```

Group by 'Category' and calculate the cumulative sum of 'Sales' within each category.


### Grouping with Multiple Aggregations

```python
df.groupby('Category').agg({'Price': ['mean', 'sum'], 'Quantity': 'max'})
```
Group by 'Category', calculate mean and sum of 'Price', and max of 'Quantity'.

### Grouping and Percentage Change

```python
df.groupby('Department')['EmployeeCount'].pct_change()
```

Group by 'Department' and calculate the percentage change of 'EmployeeCount'.

2 / 2