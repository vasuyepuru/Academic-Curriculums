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

```
from sklearn.cluster import KMeans
import numpy as np

# Sample data: Customer spending behavior (annual spending on two categories)
data = np.array([[200, 300], [500, 700], [800, 900], [400, 600], [300, 400]])

# Create and fit the model
kmeans = KMeans(n_clusters=2)
kmeans.fit(data)

# Print cluster assignments
print(f"Cluster assignments: {kmeans.labels_}")

```
Real-World Example:
K-Means clustering is used in customer segmentation, such as grouping customers based on spending patterns or preferences for targeted marketing.

4. Neural Networks
Example: Predicting Handwritten Digits (MNIST Dataset)
```
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Flatten
from tensorflow.keras.datasets import mnist
from tensorflow.keras.utils import to_categorical

# Load MNIST dataset
(X_train, y_train), (X_test, y_test) = mnist.load_data()
X_train, X_test = X_train / 255.0, X_test / 255.0  # Normalize
y_train, y_test = to_categorical(y_train), to_categorical(y_test)

# Build the neural network
model = Sequential([
    Flatten(input_shape=(28, 28)),
    Dense(128, activation='relu'),
    Dense(10, activation='softmax')
])

# Compile and train the model
model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
model.fit(X_train, y_train, epochs=5)

# Evaluate the model
accuracy = model.evaluate(X_test, y_test, verbose=0)[1]
print(f"Test Accuracy: {accuracy * 100:.2f}%")

```
Real-World Example:
Neural networks are widely applied in image recognition, such as identifying handwritten digits for postal mail automation or check processing in banks.


