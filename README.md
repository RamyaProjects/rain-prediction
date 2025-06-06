# Rain Prediction using Neural Networks
This project aims to predict whether it will rain tomorrow based on historical weather data using a Neural Network (NN) classifier. The data was preprocessed and modeled using TensorFlow/Keras to build a robust binary classification model.

**Dataset & Features**

The dataset includes various weather-related features such as:

- Temperature
- Humidity
- Wind speed and direction
- RainToday (Yes/No)
- Pressure
- Sunshine
- Cloud cover, etc.
- Target Variable:RainTomorrow – Whether it will rain the next day (Yes/No)

**Data Preprocessing**

- Mapped Yes/No to 1/0 in RainToday and RainTomorrow.
- Dropped non-informative columns like Date.
- Handled categorical variables using LabelEncoder.
- Normalized all features using StandardScaler.

**Model Architecture**

The model is a feedforward neural network built using Keras:


-  Input Layer  : Output Shape- (21,) ,              21 input features (scaled)                          
-  Dense Layer :  Output Shape- (32,)      ,activation function:   ReLU ,       Fully connected layer with 32 units                 
-  Dense Layer   : Output Shape- (32,)       ,activation function:  ReLU  ,      Fully connected layer with 32 units                 
-  Dense Layer  :  Output Shape- (16,)        ,activation function: ReLU  ,      Fully connected layer with 16 units                 
-  Dropout Layer : Output Shape- (16,)                 Dropout with 25% rate to prevent overfitting        
-  Dense Layer   : Output Shape- (10,)       ,activation function:  ReLU ,       Fully connected layer with 10 units                 
-  Dropout Layer : Output Shape- (10,)              Dropout with 50% rate                               
-  Output Layer  : Output Shape- (1,)        ,activation function:  Sigmoid   , Outputs probability of rain (binary classification) 



- Optimizer: Adam (learning rate = 0.0009)
- Loss: binary_crossentropy
- Metrics: accuracy
- Early stopping with patience=20 and min_delta=0.001

**Training**
- Epochs: 150 (early stopping kicked in at epoch 35)
- Batch size: 32
- Validation split: 20%

**Evaluation**

Test Set Metrics:

- Accuracy	84.98%
- Precision	73.80%
- Recall	49.50%
- F1 Score	59.26%
- Confusion matrix and training/validation loss curves were plotted for detailed insight.

**Visualizations**

- Loss curve (Training vs. Validation)
- Accuracy curve (Training vs. Validation)
- Confusion matrix (Visualized with sns.heatmap)

**Conclusion**
The model performs reasonably well in predicting rainfall with high precision but moderate recall, which is typical for slightly imbalanced datasets. With further feature engineering or ensemble methods, recall can be improved.

