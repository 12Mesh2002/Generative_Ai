# Fast Style Transfer

## Overview

This repository implements fast style transfer using a residual autoencoder network, instance normalization, and VGG19 for perceptual loss. The network takes a content image as input and produces a stylized image.

## Training Insights

- **Feedforward Network:**
  We use a residual autoencoder network, the same one employed in the original implementation. This network takes a content image as input and produces a stylized image.

- **Loss Function:**
  The loss function, as defined in the [Gatys et al. paper](https://arxiv.org/pdf/1508.06576.pdf), remains crucial. It comprises both style and content loss.

- **Normalization Technique:**
  Instead of batch normalization, we opt for instance normalization, following the findings of the paper titled [Instance Normalization: The Missing Ingredient for Fast Stylization](https://arxiv.org/abs/1607.08022). This choice often yields superior results.

- **Perceptual Loss:**
  VGG19 comes into play for calculating perceptual loss, a critical aspect discussed in the original paper. This loss is instrumental in ensuring that the generated images capture the style essence effectively.

## Getting Started

1. **Download the Kaggle Dataset:**
   - You can just go to this url and download the dataset manually from kaggle: [https://www.kaggle.com/datasets/arnaud58/landscape-pictures](https://www.kaggle.com/datasets/arnaud58/landscape-pictures)
   - Extract the downloaded zip file. 

2. **Update Dataset Path in Code:**
   - Open the provided code in your preferred editor.
   - Update the `dataset_path` variable to point to the correct location where the dataset is stored on your system.
     ```python
     dataset_path = "/path/to/your/dataset"
     ```
3. **Download Pre-trained Model
   -To use the pre-trained weights for testing,Save the downloaded model checkpoint file ('model_checkpoint.ckpt') to your local machine.

5. **Run the Code:**
   - Execute the code to set up a TensorFlow dataset loader using the specified parameters.
   - The `TensorflowDatasetLoader` class should be defined somewhere in your code or imported from a module.
   - The code prints the element spec of the training and testing datasets, providing insights into the structure of the data.
     
## Limitations

### 1. Computational Resources

Training and generating stylized images using deep neural networks can be computationally intensive. Users should ensure their hardware, especially GPU capabilities, meets the requirements for reasonable training times.

### 2. Training Time

Training a deep neural network for style transfer can take a significant amount of time, depending on the complexity of the network architecture, dataset size, and other factors. Users should be prepared for long training times and consider using pre-trained models if time is a constraint.

### 3. Dataset Limitations

The quality of stylized images heavily depends on the diversity and quality of the dataset used for training. If the dataset is not representative of various artistic styles, the model might struggle to generalize to different styles.

### 4. Style Transfer Artefacts

Fast style transfer methods might introduce artifacts in the stylized images, such as over-smoothing or distortions. Users should be aware that achieving a perfect stylization without any artifacts is a challenging task and may require additional fine-tuning.

### 5. Style-Content Trade-off

Striking a balance between preserving the content of the input image and effectively capturing the style can be challenging. Some styles may lead to more pronounced alterations in content, and users should be aware of this trade-off.

### 6. Hyperparameter Sensitivity

The performance of the model may be sensitive to hyperparameter choices. Users might need to experiment with learning rates, batch sizes, and other hyperparameters to achieve optimal results for their specific use case.

### 7. Memory Consumption

Training and running inference with deep neural networks can be memory-intensive. Users should be mindful of the available memory on their system, especially when dealing with high-resolution images or large datasets.

### 8. Generalization to New Styles

While the model may perform well on styles similar to those in the training set, generalizing to entirely new or highly abstract styles might be challenging. Users should manage expectations regarding the range of styles the model can effectively transfer.

## Citations

- Gatys, L. A., Ecker, A. S., & Bethge, M. (2016). A Neural Algorithm of Artistic Style. arXiv preprint arXiv:1508.06576.
- Ulyanov, D., Vedaldi, A., & Lempitsky, V. (2016). Instance Normalization: The Missing Ingredient for Fast Stylization. arXiv preprint arXiv:1607.08022.
