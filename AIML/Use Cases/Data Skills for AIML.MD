Here's a Python code example that demonstrates data preprocessing, data visualization, and data cleaning using the provided dataset

Note : [Use Netflix Dataset here](https://github.com/vasuyepuru/Academic-Curriculums/tree/main/AIML/DataSets) 

Python Code

```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
file_path = 'netflix.csv'  # Replace this with the path to your dataset file
data = pd.read_csv(file_path)

# Data Preprocessing
print("Dataset Overview:")
print(data.info())

# Handling missing values
print("\nHandling Missing Values:")
data['user_rating_score'].fillna(data['user_rating_score'].mean(), inplace=True)
data['ratingdescription'].fillna("Unknown", inplace=True)
print(data.isnull().sum())

# Converting release year to datetime (if needed for time-based analysis)
data['release_year'] = pd.to_datetime(data['release_year'], format='%Y')

# Data Cleaning
print("\nCleaning Data:")
# Removing duplicate rows
data = data.drop_duplicates()
print(f"Duplicate Rows Removed. Remaining Rows: {len(data)}")

# Checking for invalid data in user ratings
invalid_scores = data[data['user_rating_score'] > 100]  # Example threshold check
print(f"\nInvalid Scores Found:\n{invalid_scores}")

# Data Visualization
print("\nData Visualization:")

# Plotting distribution of user ratings
plt.figure(figsize=(10, 5))
sns.histplot(data['user_rating_score'], bins=20, kde=True, color='blue')
plt.title('Distribution of User Ratings')
plt.xlabel('User Ratings')
plt.ylabel('Frequency')
plt.show()

# Plotting rating levels by release year
plt.figure(figsize=(12, 6))
sns.countplot(data=data, x='release_year', hue='ratinglevel', palette='viridis')
plt.title('Rating Levels Over the Years')
plt.xlabel('Release Year')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.show()

# Plotting top 10 movies/series by user rating size
top_rated = data.nlargest(10, 'user_rating_size')
plt.figure(figsize=(12, 6))
sns.barplot(data=top_rated, x='title', y='user_rating_size', palette='mako')
plt.title('Top 10 Titles by User Rating Size')
plt.xlabel('Title')
plt.ylabel('User Rating Size')
plt.xticks(rotation=45)
plt.show()

```





1. Data Preprocessing

Example: Handling missing values and converting data types.

```
import pandas as pd

# Load the dataset
data = pd.read_csv('netflix.csv')

# Check for missing values
print("Missing values before handling:")
print(data.isnull().sum())

# Fill missing values in 'user_rating_score' with the column mean
data['user_rating_score'].fillna(data['user_rating_score'].mean(), inplace=True)

# Fill missing values in 'ratingdescription' with a default value
data['ratingdescription'].fillna("Unknown", inplace=True)

# Check data types and convert 'release_year' to datetime
data['release_year'] = pd.to_datetime(data['release_year'], format='%Y', errors='coerce')

print("Missing values after handling:")
print(data.isnull().sum())
```

2. Data Visualization

Example: Visualizing the distribution of user_rating_score.

```
import seaborn as sns
import matplotlib.pyplot as plt

# Plot the distribution of user rating scores
plt.figure(figsize=(10, 5))
sns.histplot(data['user_rating_score'], bins=20, kde=True, color='blue')
plt.title('Distribution of User Ratings')
plt.xlabel('User Rating Score')
plt.ylabel('Frequency')
plt.show()

# Visualize rating levels over years
plt.figure(figsize=(12, 6))
sns.countplot(data=data, x='release_year', hue='ratinglevel', palette='viridis')
plt.title('Rating Levels Over the Years')
plt.xlabel('Release Year')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.show()
```

3. Data Cleaning

Example: Removing duplicate rows and handling invalid data.

```
# Remove duplicate rows
print(f"Rows before removing duplicates: {len(data)}")
data = data.drop_duplicates()
print(f"Rows after removing duplicates: {len(data)}")

# Example of finding invalid data in 'user_rating_score'
invalid_scores = data[data['user_rating_score'] > 100]  # Assuming 100 is the max valid score
print("Invalid user rating scores:")
print(invalid_scores)

# Drop rows with invalid user rating scores (if any)
data = data[data['user_rating_score'] <= 100]
print(f"Rows after cleaning invalid scores: {len(data)}")

```
