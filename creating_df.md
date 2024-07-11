# Creating Pandas Dataframe

import pandas as pd

# Define schema
schema = {
    'name': str,
    'age': int,
    'city': str,
    'height': float
}

# Example data
data = {
    'name': ['Alice', 'Bob', 'Charlie'],
    'age': [25, 30, 35],
    'city': ['New York', 'Los Angeles', 'Chicago'],
    'height': [5.6, 6.0, 5.8]
}

# Create DataFrame with schema
df = pd.DataFrame(data)

# Optional: Assign specific data types to columns after DataFrame creation
df = df.astype(schema)


# Change DataType
df['height'] = df['height'].astype(int)

# column rename
df = df.rename(columns={'name': 'Name'})

# Add a new column 'E' with list values at position 1 (after column 'A')
df.insert(1, 'E', [True, False, True])

# Drop column 'E' using drop() method
df_drop = df.drop(columns=['E'])


# Select columns 'name' and 'city'
df_selected = df_drop[['Name', 'city']]


# To Print Schema
print(df_selected.info())

# To Print Schema
print(df_selected.dtypes)
