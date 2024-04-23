# Exercise 1: CNN Model for Image Classification

In this markdown file, we will discuss the results of the CNN model for image classification. The model was trained on the CIFAR-10 dataset, 
which consists of 60,000 32x32 color images in 10 classes, with 6,000 images per class. The dataset is divided into 50,000 training images and 10,000 testing images.

| Model ID | Description                               | Batch Size | Epochs | Learning Rate | Dropout Rate | Accuracy | Other Parameters | 
|----------|-------------------------------------------|------------|--------|---------------|--------------|----------|------------------|
| 1        | Basic CNN Model                           | 64         | 10     | 0.001         | 0.2          | 81,65%   | -                |
| 2        | Basic CNN Model and smaller learning rate | 64         | 10     | 0.0001        | 0.2          | 71,62%   | -                |
| 3        | Basic CNN Model and bigger learning rate  | 64         | 10     | 0.01        | 0.2          | 74,99%   | -                |
| 4        | CNN with bigger batch size                | 128        | 30     | 0.001        | 0.2          | 80.14%   | -                |
| 5        | CNN more personalised                     | 128         | 30     | 0.001         | 0.3          | 86.19%      | -                |

Here are our comments on the results:

**Learning Rate Variations**:

- Lowering the learning rate (Model 2) resulted in a significantly lower accuracy compared to the baseline. This suggests that the model requires either more epochs to converge or a slight increase in the learning rate to achieve better performance within the same number of epochs.
- Increasing the learning rate (Model 3), on the other hand, showed an improvement over the lowered rate but still underperformed relative to the baseline.

**Batch Size Variations**:

Increasing the batch size (Model 4) generally reduces the noise in the gradient estimates but can also affect the generalization ability of the model. In this case, a larger batch size did not result in a significant improvement, indicating a potential trade-off between training stability and model effectiveness (a little bit of faster in training).

**Model Personalization**:

Increasing both the number of epochs and the dropout rate (Model 5) led to the highest accuracy among the tested configurations. This suggests that allowing more training time along with higher regularization (via increased dropout) can effectively combat overfitting, leading to a model that generalizes better on the test data.

In conclusion, the basic CNN model with a moderate learning rate, batch size, and dropout rate can achieve good performance on the CIFAR-10 dataset. However, further tuning and personalization of the model can lead to even better results, as demonstrated by the improved accuracy in Model 5.

# Exercise 2 : Analysis of a Deep Architecture

Link of the paper : https://arxiv.org/pdf/1602.07261.pdf

**Questions** : Re-explain in few phrases what you understood from the architecture doing comparison
with the architectures presented in the class.

Inception-v4 is the fourth iteration of this model. It is more efficient due to an architecture that is more uniform and better organized. It is also more effective in managing computational resources, which goes into increased speed in image data processing while maintaining high accuracy. Its connection to ResNet is primarily conceptual, in that Inception-v4 incorporates ideas of modularity and efficiency from connections, though it does not directly use the characteristic residual connections of ResNet. This integration allows it to benefit from some of the advantages of residual architectures, such as improved gradient propagation, without complicating the architecture with additional connections.


# Exercise 3 : Optional : Review Questions

a) Explain the notion of hierarchical features with CNNs.
When we use Convolutional Neural Networks (CNNs) for tasks like recognizing images, the network learns to understand the image in layers. Each layer of the network picks up on different features of the image. The first layer might just recognize simple patterns like edges and colors. As you go deeper into the network, the layers start recognizing more complex features like shapes or specific parts of objects (like wheels or eyes). As we get in deeper layers, the network is recognizing whole objects or even scenes. 

b) Explain the main differences for the deep  architectures seen in class : AlexNet, VGGNet,
GoogLeNet, ResNet. What were their intuitions when putting together such architectures ?

- AlexNet: It consists of 5 convolutional layers followed by 3 fully connected layers. The intuition behind AlexNet was to use deep learning to learn hierarchical features from images, which could then be used for classification tasks. AlexNet also introduced the concept of using ReLU activation functions and dropout regularization to improve training speed and generalization performance.
- VGGNet: It consists of 16-19 convolutional layers followed by 3 fully connected layers. This architecture focused on deepening the network further with a uniform structure, using small, consistent filter sizes throughout which simplified the architecture but increased the parameter count.
- GoogLeNet: GoogLeNet, also known as Inception v1. It Introduced the concept of inception modules, which use filters of various sizes to capture information at different scales within the same layer. 
- ResNet: : Introduced residual connections, allowing layers to learn identity functions to preserve input across layers. This innovation supports the training of much deeper networks by helping to avoid the vanishing gradient problem

The main intuition behind these architectures was to design deep convolutional neural networks that could learn hierarchical features from images more effectively and efficiently than traditional deep networks. Each architecture introduced new ideas and techniques to improve training speed, generalization performance, and computational efficiency, leading to significant advancements in the field of deep learning.



