# Fast Style Transfer

## Overview

This repository implements fast style transfer using a residual autoencoder network, instance normalization, and VGG19 for perceptual loss. The network takes a content image as input and produces a stylized image.

## Training Insights

- **Feedforward Network:**
  We use a residual autoencoder network, similar to the original implementation.

- **Loss Function:**
  The loss function includes both style and content loss, following the Gatys et al. paper.

- **Normalization Technique:**
  Instead of batch normalization, we use instance normalization for superior results.

- **Perceptual Loss:**
  VGG19 is utilized for calculating perceptual loss, ensuring that generated images capture the style essence effectively.

## Limitations

1. **Computational Resources:**
   - Training and generating stylized images can be computationally intensive.

2. **Training Time:**
   - Training a deep neural network for style transfer can take a significant amount of time.

3. **Dataset Limitations:**
   - The quality of stylized images heavily depends on the diversity and quality of the dataset.

4. **Style Transfer Artefacts:**
   - Fast style transfer methods might introduce artifacts in the stylized images.

5. **Style-Content Trade-off:**
   - Striking a balance between preserving content and capturing style can be challenging.

6. **Hyperparameter Sensitivity:**
   - The performance of the model may be sensitive to hyperparameter choices.

7. **Memory Consumption:**
   - Training and running inference can be memory-intensive.

8. **Generalization to New Styles:**
   - Generalizing to entirely new or highly abstract styles might be challenging.

## Getting Started

...

## Usage

...

