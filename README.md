# Neural Style Transfer with PyTorch

This project demonstrates neural style transfer using a pre-trained VGG-19 model in PyTorch. Neural style transfer is a technique that blends the content of one image with the style of another, creating an artistic, stylized output.

## Overview

This repository provides code for loading content and style images, extracting feature maps, calculating content and style losses, and optimizing an output image to resemble the style of one image while retaining the content of another. The code uses a pre-trained VGG-19 network as a feature extractor and optimizes the content image to match the desired style image using gradient descent.

## Requirements

- Python 3.6 or higher
- PyTorch
- torchvision
- numpy
- matplotlib
- imageio
- PIL (Pillow)

Install dependencies with:

```bash
pip install torch torchvision numpy matplotlib imageio pillow
```

## Project Structure

- `content_path`: Path to the content image (image to preserve content from).
- `style_path`: Path to the style image (image to take artistic style from).
- `get_feature_output`: Extracts feature maps from specified layers of VGG-19.
- `gram_matrix`: Computes the Gram matrix, used to capture style representation.
- `target`: Image to optimize, initialized as a clone of the content image.

## Running the Code

1. **Set up content and style images:**
   Place your content and style images in the `./images/` directory or adjust the paths accordingly.

2. **Run the Script:**
   The script will load the images, extract features, compute losses, and iteratively update the target image.

3. **Display Results:**
   Every 500 epochs, the script displays an intermediate output image and logs the loss value.

## Usage

Simply place your desired images in the `./images` folder and update `content_path` and `style_path` in the code. Then, run the script:

```bash
python neural_style_transfer.py
```

Sample output images are saved in the `./output/` directory.

## Key Parameters

- `style_weights`: Defines the weights for the style layers.
- `content_weight`: Weight applied to content loss.
- `style_weight`: Weight applied to style loss.
- `epochs`: Number of iterations to run the optimization.
- `checkpoint`: Number of epochs between displaying intermediate results.

## Example

### Input

| Content Image  | Style Image        |
|----------------|--------------------|
| ![Content](images/janelle.png) | ![Style](images/Starry-Night-by-Vincent-Van-Gogh-painting.jpg) |

### Output

| Stylized Output |
|-----------------|
| ![Output](output/target_image.jpg) |

## References

- [Gatys et al. (2015)](https://arxiv.org/abs/1508.06576): "A Neural Algorithm of Artistic Style"
- [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)

---

