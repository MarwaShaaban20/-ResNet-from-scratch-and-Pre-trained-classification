### Description

This project implements a ResNet using TensorFlow and Keras to classify handwritten digits from the MNIST dataset. The project contains two primary sections:

1. **Custom ResNet Model**
2. **Pre-trained ResNet50 Model with Fine-Tuning**

#### 1. Custom ResNet Model

In this section, we build a custom Residual Network (ResNet) model from scratch, train it on the MNIST dataset, and evaluate its performance. Residual Networks are known for their ability to train very deep networks by addressing the vanishing gradient problem through shortcut connections.

**Code Highlights:**

- **Residual Block Definition:** A residual block is defined using two convolutional layers, batch normalization, and ReLU activation, with a shortcut connection to enable gradient flow.
- **ResNet Model Construction:** The ResNet model is constructed by stacking multiple residual blocks. Initial layers include a convolutional layer, batch normalization, ReLU activation, and max-pooling. The model ends with a global average pooling layer and a fully connected softmax layer.
- **Model Compilation:** The model is compiled using the Adam optimizer and categorical cross-entropy loss.
- **Data Preparation:** The MNIST dataset is loaded, normalized, and converted to a categorical format.
- **Model Training:** The model is trained on the MNIST training set and validated on the test set.

#### 2. Pre-trained ResNet50 Model with Fine-Tuning

In this section, we use a pre-trained ResNet50 model from Keras applications, modify it to fit the MNIST dataset, and fine-tune the dense layers.

**Code Highlights:**

- **Loading Pre-trained Model:** The ResNet50 model is loaded with ImageNet weights, excluding the top fully connected layers.
- **Model Modification:** Additional dense layers are added for feature extraction and classification.
- **Freezing Layers:** All layers except the new dense layers are frozen to retain pre-trained weights.
- **Data Preparation:** The MNIST dataset is resized to fit the input shape of ResNet50, converted to 3 channels, normalized, and converted to categorical format.
- **Model Compilation:** The modified model is compiled using the Adam optimizer and categorical cross-entropy loss.
- **Model Training:** The model is trained on the resized MNIST dataset and validated on the test set.

