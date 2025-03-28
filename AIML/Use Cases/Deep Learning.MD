Neural networks and their advanced architectures—like CNNs, RNNs, LSTMs, and GANs—play a pivotal role in real-time applications across numerous industries. Let's focus on the automotive industry as our example domain, particularly its applications in autonomous driving and smart vehicle systems.

1. Neural Networks

Use in Automotive: Neural networks are the foundation for vehicle behavior modeling, such as predicting traffic flow or detecting road signs.

Python Example:

```
from keras.models import Sequential
from keras.layers import Dense
import numpy as np

# Sample data (e.g., [Speed, Distance to object])
X = np.array([[50, 10], [60, 5], [30, 20]])  # Features
y = np.array([1, 0, 1])  # Labels: 1=Safe driving, 0=Unsafe

# Neural Network Model
model = Sequential()
model.add(Dense(10, activation='relu', input_dim=2))
model.add(Dense(1, activation='sigmoid'))
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
model.fit(X, y, epochs=10, verbose=0)
prediction = model.predict(np.array([[45, 15]]))
print("Driving Safety Prediction:", prediction)
```

2. Convolutional Neural Networks (CNNs)

Use in Automotive: CNNs are used for image processing tasks such as recognizing pedestrians, vehicles, or lane markings from camera input.

Python Example:

```
from keras.models import Sequential
from keras.layers import Conv2D, MaxPooling2D, Flatten, Dense

# CNN Model for Image Classification
model = Sequential()
model.add(Conv2D(32, kernel_size=(3, 3), activation='relu', input_shape=(64, 64, 3)))
model.add(MaxPooling2D(pool_size=(2, 2)))
model.add(Flatten())
model.add(Dense(128, activation='relu'))
model.add(Dense(1, activation='sigmoid'))
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
# Assume input data prepared for training as images
```

3. Recurrent Neural Networks (RNNs)

Use in Automotive: RNNs process sequential data, enabling prediction of driver behavior patterns or real-time navigation based on GPS data.

Python Example:

```
from keras.models import Sequential
from keras.layers import SimpleRNN, Dense
import numpy as np

# Sequential Data
X = np.random.random((10, 5, 1))  # Example of 10 sequences, each with 5 time steps and 1 feature
y = np.random.randint(2, size=(10, 1))  # Binary labels

# RNN Model
model = Sequential()
model.add(SimpleRNN(10, activation='relu', input_shape=(5, 1)))
model.add(Dense(1, activation='sigmoid'))
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
model.fit(X, y, epochs=10, verbose=0)
```

4. Long Short-Term Memory (LSTM)

Use in Automotive: LSTMs, a type of RNN, handle time-series data like detecting anomalies in engine performance or fuel consumption over time.

Python Example:

```
from keras.models import Sequential
from keras.layers import LSTM, Dense
import numpy as np

# Time-series Data
X = np.random.random((10, 5, 1))  # Example of 10 sequences, each with 5 time steps and 1 feature
y = np.random.randint(2, size=(10, 1))  # Binary labels

# LSTM Model
model = Sequential()
model.add(LSTM(10, activation='relu', input_shape=(5, 1)))
model.add(Dense(1, activation='sigmoid'))
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
model.fit(X, y, epochs=10, verbose=0)
```

5. Generative Adversarial Networks (GANs)

Use in Automotive: GANs generate synthetic data for training models, such as simulating traffic scenarios for autonomous vehicle learning.

Python Example:

```
from keras.models import Sequential
from keras.layers import Dense

# Generator
generator = Sequential()
generator.add(Dense(128, activation='relu', input_dim=100))
generator.add(Dense(784, activation='sigmoid'))

# Discriminator
discriminator = Sequential()
discriminator.add(Dense(128, activation='relu', input_dim=784))
discriminator.add(Dense(1, activation='sigmoid'))

generator.compile(optimizer='adam', loss='binary_crossentropy')
discriminator.compile(optimizer='adam', loss='binary_crossentropy)

print("GAN components ready for training synthetic data.")
```
These architectures are instrumental in developing autonomous vehicles, intelligent traffic management systems, and fuel-efficient engines, among other innovations.
