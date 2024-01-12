# Image Classification with MobileNet

## Overview

This project uses a pretrained MobileNet model to classify images. MobileNet is a compact and efficient model well-suited for mobile applications.

The model is used to make predictions on sample images to identify common objects like animals, foods, and household items. 

## Usage

1. Load and preprocess image:

```python
img = load_img('image.jpg', target_size=(224, 224)) 
img_array = img_to_array(img)
preprocessed_img = mobilenet.preprocess_input(img_array)
```

2. Make prediction:

```python
model = MobileNet()
prediction = model.predict(preprocessed_img)
```

3. Decode prediction:

```python 
results = decode_predictions(prediction)
print(results[0][0]) # prints ('label', 'probability')
```

## Examples

Classified an image of an American chameleon as "American chameleon" with 65% probability.

Classified an image of an espresso as "espresso" with 98% probability.

Classified an image of a strawberry as "strawberry" with 100% probability.

## References

- [MobileNet Paper](https://arxiv.org/abs/1704.04861)
- [Keras Applications](https://keras.io/api/applications/)