# Cat vs Dog Image Classification

## Overview

This project trains a convolutional neural network (CNN) to classify images as either cats or dogs. The model is trained on 1000 images (500 cats, 500 dogs) and evaluated on a test set of 100 images (50 cats, 50 dogs).

Two models are developed:

1. A custom CNN model built from scratch
2. A pretrained VGG16 model fine-tuned on the cat vs dog dataset 

## Models

### Custom CNN

The custom CNN model consists of the following layers:

- 2D convolution layers
- Max pooling layers 
- Flatten layer
- Dense layer with softmax activation

### Fine-Tuned VGG16 

The VGG16 model pretrained on ImageNet is used as a base model. The fully-connected layers at the end are removed and replaced with a Dense layer with softmax activation for cat vs dog classification. The pretrained weights are frozen, making only the new output layer trainable during fine-tuning.

## Data Pipeline

The raw cat and dog images are split into train, validation, and test sets. Image augmentation is applied to the training data using rotations, shifts, shears, zooms, and flips. 

ImageGenerator flows are used to efficiently load and preprocess batches of images during training and evaluation.

## Training

Both models are trained for 5 epochs with categorical cross-entropy loss, Adam optimizer, and accuracy metric.

## Evaluation

The final models are evaluated on the held-out test set of 100 images. The fine-tuned VGG16 model achieves 99% accuracy on the test set.

## Usage

The trained models can be loaded and used to predict if a new image contains a cat or a dog.

Example:

```python
img = preprocess(load_img('cat.jpg'))
model = load_model('cats_vs_dogs_model.h5') 
prediction = model.predict(img)
print(prediction) # [0.99, 0.01] -> cat