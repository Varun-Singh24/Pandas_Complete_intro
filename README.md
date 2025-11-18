

## 🚀 Notebook Overview

The notebook demonstrates four key stages of data handling with pandas.

### 1\. Environment Setup and Imports

The session starts by importing the necessary libraries under their conventional aliases:

| Library | Alias | Purpose |
| :--- | :--- | :--- |
| **pandas** | `pd` | Data structure (DataFrame) and analysis tools. |
| **NumPy** | `np` | Foundation for numerical computing in Python. |
| **Matplotlib** | `plt` | Plotting and visualization. |

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

-----

### 2\. Creating a Pandas DataFrame

The **DataFrame** is the primary two-dimensional data structure in pandas. It is typically created from dictionaries, where keys map to column names and values are lists of data.

#### Example: Basic DataFrame Creation

```python
df = pd.DataFrame(
    {
        "Name": [
            "Varun, Mr harris",
            "Allen",
            "Bob John"
        ],
        "Age" : [22, 35, 58],
        "Sex" : ["male", "male", "male"]
    }
)
print(df)
```

**Output:**

```
               Name  Age   Sex
0  Varun, Mr harris   22  male
1             Allen   35  male
2          Bob John   58  male
```


### 3\. Data Loading and Aggregation

The notebook then loads the well-known **Titanic dataset** from a public URL to perform analysis.

#### Loading Data

The `pd.read_csv()` function is used to load data directly into a DataFrame.

```python
# Load the Titanic dataset
titanic = pd.read_csv("[https://web.stanford.edu/class/archive/cs/cs109/cs109.1166/stuff/titanic.csv](https://web.stanford.edu/class/archive/cs/cs109/cs109.1166/stuff/titanic.csv)")

# Display the first 5 rows
print(titanic.head())
```

#### Data Aggregation with `groupby()`

To summarize data, the `groupby()` method is used, followed by an aggregation function (like `mean()`). This example calculates the average age of passengers, separated by their sex.

```python
# Calculate the mean of the Age column grouped by the Sex column
age_by_sex = titanic.groupby("Sex")["Age"].mean()
print(age_by_sex)
```

**Result:**

| Sex | Mean Age |
| :---: | :---: |
| **female** | 27.915709 |
| **male** | 30.726645 |

-----

### 4\. Data Visualization

The final section demonstrates simple visualization using pandas, which utilizes **Matplotlib** under the hood.

```python
# Import matplotlib
import matplotlib.pyplot as plt

# Plot all numerical columns against the index
titanic.plot()
plt.title("Titanic Dataset - All Numerical Features Plot")
plt.xlabel("Index")
plt.ylabel("Value")
plt.show() # Note: In a notebook, this command is often optional
```


```
