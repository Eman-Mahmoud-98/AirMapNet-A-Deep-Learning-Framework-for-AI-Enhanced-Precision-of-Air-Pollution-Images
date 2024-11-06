# AirMapNet: Smart Air Pollution Mapping Using Deep Learning
<img width="850" alt="Screenshot 2024-11-02 at 9 58 32 PM" src="https://github.com/user-attachments/assets/7d7ac808-5bc5-41a0-918b-24177d518c77">


The proposed model architecture is defined to predict multiple output values, namely AQI, PM2.5, PM10, O3, and NO2, simultaneously. The key components are described below.

LeakyReLU Activation: This is the activation introduced in all convolutional and dense layers; it may avoid some problems, like the "dying ReLU" problem since it allows a small, non-zero gradient when the input is negative.

Input Layer: Architecture takes images as input with a shape of (224, 224, 3).

Convolutional Blocks and Residual Connections:
- Block 1 contains two Conv2D layers with 64 filters, followed by a MaxPooling layer.
- Block 2 contains two Conv2D layers with 128 filters, followed by a MaxPooling layer.
- Block 3-5 each contain a residual connection from the output of a Conv2D layer with 128 filters added back to the block input. Each block also ends with a MaxPooling layer.

Fully Connected Layers: After flattening the output, two dense layers of 256 and 128 neurons were added along with LeakyReLU activation.

Output Layer: AQI, PM2.5, PM10, O3, and NO2 predictions were done through different output layers, each consisting of one neuron and linear activation.

Compilation: The model designates the root mean squared error, for the loss function of each output. The Adam optimizer is employed with a learning rate of 1e-4.
