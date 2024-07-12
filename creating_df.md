# Creating Pandas Dataframe

import pandas as pd

## Define schema
schema = {
    'name': str,
    'age': int,
    'city': str,
    'height': float
}

## Example data
data = { <br>
    'name': ['Alice', 'Bob', 'Charlie'],<br>
    'age': [25, 30, 35],<br>
    'city': ['New York', 'Los Angeles', 'Chicago'],<br>
    'height': [5.6, 6.0, 5.8]<br>
}<br>

## Create DataFrame with schema
df = pd.DataFrame(data)

## Optional: Assign specific data types to columns after DataFrame creation
df = df.astype(schema)


## Change DataType
df['height'] = df['height'].astype(int)

## column rename
df = df.rename(columns={'name': 'Name'})

## Add a new column 'E' with list values at position 1 (after column 'A')
df.insert(1, 'E', [True, False, True])

## Drop column 'E' using drop() method
df_drop = df.drop(columns=['E'])


## Select columns 'name' and 'city'
df_selected = df_drop[['Name', 'city']]


## To Print Schema
print(df_selected.info())

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 3 entries, 0 to 2
Data columns (total 2 columns):

|   #   |  Column  |  Non-Null Count  |  Dtype  |
|:-----:|:--------:|:----------------:|:-------:|
|   0   |   Name   |      3 non-null      |  object  |
|   1   |   city   |      3 non-null      |  object  |

dtypes: object(2)
memory usage: 176.0+ bytes
None


## To Print Schema
print(df_selected.dtypes)

| Column | Data Type |
|--------|-----------|
| Name   | object    |
| city   | object    | 


## print data
print(df_Selected)

|   Name   |    City     |
|:--------:|:-----------:|
|  Alice   |  New York   |
|   Bob    | Los Angeles |
| Charlie  |   Chicago   |
