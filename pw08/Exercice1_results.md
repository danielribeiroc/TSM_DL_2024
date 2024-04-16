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
