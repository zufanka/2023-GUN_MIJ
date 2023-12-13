# Example usage of `.query()`
### Basic query
```python
df.query('Age > 30')
```
This query selects rows where the 'Age' column is greater than 30.

### Using the ~ Operator for Negation

```python
df.query('~(Age < 30)')
```
This selects rows where 'Age' is not less than 30 (i.e., 30 or older).

### Query with Multiple Conditions
```python
df.query('Age > 30 and Gender == "Male"')
```
This selects rows where 'Age' is greater than 30 and the 'Gender' is Male.

### Using OR Operator

```python
df.query('Age < 18 or Age > 60')
```
This query selects rows where 'Age' is either less than 18 or greater than 60.

### Using String Methods

```python
df.query('Name.str.startswith("A")')
```
Selects rows where the 'Name' column starts with the letter 'A'.

```python
df.query('Name.str.contains("Smith")')
```
Selects rows where the 'Name' contains the substring "Smith".

### Query with Variable:

``` python
max_age = 50
df.query('Age == @max_age')
```
This uses an external variable (max_age) in the query.

### Not Equal Condition:

```python
df.query('City != "New York"')
```
Selects rows where the 'City' column is not 'New York'.


### Using Less Than or Equal To:

```python
df.query('Age <= 20')
```
This selects rows where 'Age' is less than or equal to 20.

### Using in Keyword:

```python
df.query('Department in ["Sales", "Marketing"]')
```
This selects rows where the 'Department' is either 'Sales' or 'Marketing'.

### Using not in Keyword:

```python
df.query('Department not in ["HR", "Finance"]')
```
Selects rows where 'Department' is neither 'HR' nor 'Finance'.

### Chaining Queries:
``` python
df.query('Age > 25').query('Salary > 50000')
```
This applies two filters sequentially, first for 'Age' greater than 25 and then for 'Salary' greater than 50,000.

### Comparing Columns:
```python
df.query('Salary > Bonus')
```
This selects rows where the 'Salary' column value is greater than the 'Bonus' column value.

### Using Backticks for Column Names with Spaces:

```python
df.query('`Total Sales` > 10000')
```
For column names with spaces, use backticks to enclose the column name.


### Combining Queries with Parentheses

```python
df.query('(Age < 20) or (Age > 60 and Gender == "Female")')
```

### Querying with Datetime Conditions

```python
df.query('Date > "2023-01-01"')
```
This selects rows where the 'Date' column is after January 1st, 2023.

### Querying with Null/NaN Values

```python
df.query('Address.isnull()', engine='python')
```
This selects rows where the 'Address' column contains Null or NaN values. Note the use of engine='python' for such queries.
