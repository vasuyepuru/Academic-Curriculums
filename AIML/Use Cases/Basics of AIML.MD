1. Machine Learning Algorithms
Example: Linear Regression in Python (Supervised Learning)

```
from sklearn.linear_model import LinearRegression
import numpy as np

# Sample data: House size (in square feet) and price (in $1000s)
X = np.array([[1500], [2000], [2500], [3000], [3500]])
y = np.array([300, 400, 500, 600, 700])

# Create and train the model
model = LinearRegression()
model.fit(X, y)

# Predict house price for a 2800 sq. ft. house
predicted_price = model.predict([[2800]])
print(f"Predicted Price: {predicted_price[0]}k")
```

Real-World Example:
Linear regression is used in real estate to predict house prices based on features like size, number of rooms, location, etc.

2. Supervised Learning
Example: Classification with Decision Trees

```
from sklearn.tree import DecisionTreeClassifier

# Training data: Features (age, income) and labels (buy or not buy)
X = [[25, 50000], [30, 60000], [35, 70000], [40, 80000]]
y = ['No', 'No', 'Yes', 'Yes']

# Create and train the decision tree model
classifier = DecisionTreeClassifier()
classifier.fit(X, y)

# Predict if a 29-year-old with 55,000 income will buy
prediction = classifier.predict([[29, 55000]])
print(f"Prediction: {prediction[0]}")

```
Real-World Example:
This can be applied in marketing, where companies predict whether a customer is likely to purchase a product.

3. Unsupervised Learning
Example: Clustering with K-Means

Real-World Example:
K-Means clustering is used in customer segmentation, such as grouping customers based on spending patterns or preferences for targeted marketing.

4. Neural Networks
Example: Predicting Handwritten Digits (MNIST Dataset)

Real-World Example:
Neural networks are widely applied in image recognition, such as identifying handwritten digits for postal mail automation or check processing in banks.

These examples showcase the power of machine learning for solv
