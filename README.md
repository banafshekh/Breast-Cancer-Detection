# Breast-Cancer-Detection

Building a detection model using a convolutional neural network in Tensorflow & Keras.

Used a Breast images dataset founded on Kaggle. You can find it on https://web.inf.ufpr.br/vri/databases/breast-cancer-histopathological-database-breakhis/.

The dataset contains 2 folders: Malignant and Benign Images(2,480  benign and 5,429 malignant samples).

Getting Started

Note: sometimes viewing IPython notebooks using GitHub viewer doesn't work as expected, so you can always view them using nbviewer.
Data Augmentation:

W

hy did I use data augmentation?

Data augmentation is necessary when it comes to taclking the data imbalance issue in the data.


Data Preprocessing

For every image, the following preprocessing steps were applied:

    Resize the image to have a shape of (240, 240, 3)=(image_width, image_height, number of channels): to feed images with the same size in the neural network.
    Apply normalization: devid all of pixels into 255, so we will have a pixel between 0 and 1.

Data Split:

The data was split in two parts:

    80% of the data for training.
    20% of the data for testing.
    
    Neural Network Architecture

This is the architecture that I've built:

Neural Network Architecture

    I used DenseNet201 as the pre trained weights which is already trained in the Imagenet competition.
    The learning rate was chosen to be 0.0001.
    On top of it I used a globalaveragepooling layer followed by 50% dropouts to reduce over-fitting.
    I used batch normalization and a dense layer with 2 neurons for 2 output classes ie benign and malignant with softmax as the activation function.
    I have used Adam as the optimizer and binary-cross-entropy as the loss function. 

Why this architecture?
According to previous publications, this architecture has had the best results in 2020.

The model was trained for 20 epochs.

89% accuracy on the test set.
0.9 f1 score on the test set.
