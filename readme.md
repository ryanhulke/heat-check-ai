## Rodman AI

# Description
Rodman AI is a rebound prediction tool based on the player configurations on the court, including where the shooter is. This tool can be used by analysts and coaches to find the optimal positioning for rebounds on a given play. The user may drag around the offensive and defensive player icons to represent different shot setups, and the model will display the percentage chance that there is an offensive rebound.

# Model Architecture
Masking Layer: The Masking layer is designed to filter out any input with a value of 0. This is useful because our tensors are very sparse - of the 2,350 sqft. on a half court, only 10 of them are occupied by players, represented as 1's, and the rest would be 0.
Convolutional Layer: A Conv2D layer with 16 filters of size (30, 30) follows, equipped with relu activation to introduce non-linearity, enabling the model to learn complex patterns. The large filter size is chosen to capture broad features from the court, i.e. strategic positioning patterns.
Flattening: The flattening layer allows for transitioning from a 2D feature map to a 1D vector. This allows us to connect the convolutional layer with dense layer, enabling the synthesis of learned spatial features into a format suitable for classification.
Dense: The architecture culminates in a Dense layer with a single neuron and a sigmoid activation function. This configuration makes it adept at binary classification, determining the likelihood of an input belonging to one of two predefined categories.

Regularization: It incorporates L1L2 regularization to prevent overfitting, ensuring the model's robustness by penalizing the weights' magnitude, fostering a model that generalizes to positions not seen in the training data.

Model Accuracy Metrics: 
tbd
