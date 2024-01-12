# Sign Language Digit Image Classification

## Overview

This project trains a deep convolutional neural network to classify images of hand signs representing digits from 0 to 9. The model is trained on the Sign Language Digits Dataset.

## Data

The [Sign Language Digits Dataset](https://github.com/ardamavi/Sign-Language-Digits-Dataset) contains 2050 images belong to 10 classes (0-9 digits). The images have a black background and contain a hand clearly showing one of the 10 digit classes.

The data is split into training, validation, and testing sets as follows:

- Training: 1712 images 
- Validation: 300 images
- Test: 50 images

## Model

The model uses transfer learning with a MobileNet architecture pretrained on ImageNet. The classifier portion of MobileNet is removed and replaced with a new softmax output layer suited for the 10 sign language classes.

Image augmentation and MobileNet pre-processing is used to regularize the data. The convolutional base layers are frozen to avoid overfitting.

## Training

The model is trained for 10 epochs with categorial cross-entropy loss and an Adam optimizer. 

## Results

The model achieves:

- 99% training accuracy
- 98% validation accuracy
- 100% test accuracy

Indicating successful learning of the mapping between sign language digit images and classes.

## Usage

The model can be used to classify new digit images:

```python
img = preprocess(load_img('digit.png'))

model = load_model('sl_digit_model.h5')
prediction = model.predict(img) 

print(prediction) # prints probability scores for each digit class
```

## References

- [Sign Language Digits Dataset](https://github.com/ardamavi/Sign-Language-Digits-Dataset)
- [MobileNet Paper](https://arxiv.org/abs/1704.04861)