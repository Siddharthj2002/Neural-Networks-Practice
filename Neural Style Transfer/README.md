# Neural Style Transfer

## Overview

This project implements neural style transfer to blend the style of one image with the content of another image. The pre-trained model from TensorFlow Hub is used to perform the style transfer.

## Dependencies

- TensorFlow 
- TensorFlow Hub
- OpenCV
- Matplotlib

## Usage

1. Load content and style images
2. Preprocess images into TensorFlow tensors
3. Pass content and style images to pre-trained model 
4. Generate stylized output image

```python
content_img = load_img('content.jpg')
style_img = load_img('style.jpg')

model = hub.load('https://tfhub.dev/google/magenta/arbitrary-image-stylization-v1-256/2')

stylized_img = model(content_img, style_img)[0]
```

5. Save or display output image

## Examples

Original content image:

![Content Image](/Neural%20Style%20Transfer/images/1.png)

Original style image: 

![Original Image](/Neural%20Style%20Transfer/images/2.png)

Styled image:

![Styled Image](/Neural%20Style%20Transfer/images/3.png)

## References

- [TensorFlow Hub Model](https://tfhub.dev/google/magenta/arbitrary-image-stylization-v1-256/2)
- [Neural Style Transfer Paper](https://arxiv.org/abs/1508.06576)
