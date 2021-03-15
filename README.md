# Face image classification

Project made on my own.

Keywords: TensorFlow, CNN, data viz with Seaborn, data augmentation, face images

## Context

This project tackles binary face images classification. The classification criterion is not expressed: it is implicitly defined by the labels of the dataset.

## Data

- db_train.raw : a binary file containing 111430 face images
- label_train.txt : labels of the training images *(db_train.raw)*
- db_test.raw : a binary file containing 10130 face images without the corresponding labels

## Model 

The built model is a CNN with 3 convolutional and pooling layers in order to extract the underlying features, followed by a fully connected (or 'dense') layer for the classification step, to ultimately output a probability distribution over the 2 classes.

The model's architecture is depicted below :

*WARNING : for readability purposes, the Flatten layer output was set to 300 params in the graph, but in reality it is of shape 36x5x5=900, since it flattens the pixels of the precedent layer. A tf.keras.Model.summary() is computed in the notebook for further details.*

![model_architecture](./saved_model/model_architecture.svg)

## Score

The evaluation metric used is the mean of the errors for each class, for a score varying between [-100, 100].
I achieved a score of **82.6**