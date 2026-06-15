# Object-recognition-project
# Custom Object Classification Project

## Project Overview

The goal of this project was to explore how neural networks learn and how different hyperparameters affect training behaviour. I built a custom image classification model that classifies four common desk objects which includes pens, bottles, notebooks, and phones.

I made sure to focus on achieving the highest possible accuracy,. The objective was to understand concepts such as learning rate, optimization, batch size, dropout, empirical risk minimization, and generalization through experiments.

## Dataset

I created a custom dataset consisting of 100 images consisting of 25 images for each of my 4 selected classes.

Classes:

* Pens
* Bottles
* Notebooks
* Phones

Each class contains 25 images. The images were captured from different viewing angles, distances, and lighting conditions to ensure that the dataset was varied and the model wouldn't end up memeorizing.

The dataset was divided into training and validation sets before training the model.

## Model

The model was implemented using PyTorch. It is a fully connected neural network which was used for classification.

Architecture:

* Flatten layer
* Fully connected layer
* ReLU activation
* Output layer with 4 classes

The model was trained using cross-entropy loss.

## Experiments Performed

### Learning Rate Experiment

Two learning rates were compared:

* 0.01
* 0.001

While testing, the higher learning rate resulted in unstable training and highly oscillating loss values, giving a zig-zag training loss graph. After reducing the learning rate, a smoother training and slightly improved validation accuracy was observed. Lower learning rates produce smaller weight updates, leading to more stable training.

### Optimizer Experiment

Adam and SGD optimizers were compared.

According to initial expectations, Adam was expected to have better accuracy as it often works well on small datasets but experimentation showed better results for SGD despite starting with higher loss values. Although Adam converged faster, SGD achieved the highest validation accuracy on this dataset.

### Dropout Experiment

The models with and without dropout were compared.

Removing dropout did not significantly change validation accuracy. It might be due to the small size of the dataset or because the model is relatively simple.

### Batch Size Experiment

The batch sizes of 16 and 4 were compared.

The smaller batch size achieved lower training loss but resulted in lower validation accuracy, indicating poorer generalization.

## Results

| Experiment      | Validation Accuracy |
| --------------- | ------------------- |
| Adam (lr=0.01)  | 40%                 |
| Adam (lr=0.001) | 45%                 |
| SGD (lr=0.001)  | 50%                 |
| No Dropout      | 50%                 |
| Batch Size = 4  | 35%                 |

## Failed Experiment

The base experiment was done using Adam. It had a learning rate of 0.01 which produced unstable training behaviour. The loss curve oscillated significantly instead of decreasing smoothly. This made me come to a conclusion that the learning rate might be too high for the dataset and model being used.

## Observations

* Lower learning rates improved training stability.
* SGD achieved better validation accuracy than Adam in this project.
* Lower training loss did not always correspond to higher validation accuracy.
* Batch size influenced both convergence behaviour and generalization.
* Validation accuracy improved gradually throughout training.

## Concepts Learned

During this project I explored:

* Empirical Risk Minimization (ERM)
* Loss Functions
* Gradient Descent
* Backpropagation
* Learning Rate
* Batch Size
* Epochs
* Optimization
* Dropout
* Regularization
* Overfitting and Generalization

## Future Improvements

In the future I believe that this project can be improved by:

* Acquiring a larger dataset
* Experimenting with convolutional neural networks (CNNs)
* Applying data augmentation
* Comparing additional optimizers and architectures
* Improving validation accuracy using more advanced computer vision techniques
