# Depth Estimation using U-Net

## Overview
This project implements a **depth estimation model** using a **U-Net architecture** in PyTorch. The model takes an RGB image as input and predicts a corresponding depth map. 

## Dataset
The dataset consists of:
- **RGB Images**
- **Depth Maps**

The dataset is preprocessed using `torchvision.transforms`, and DataLoader is used to manage batch processing.

## Model Architecture
The model is based on a **U-Net encoder-decoder architecture**:
- **Encoder**: Sequential convolutional blocks with increasing channels (64 → 128 → 256 → 512) and max-pooling.
- **Bottleneck**: A deeper convolutional layer with 1024 channels.
- **Decoder**: Upsampling with transposed convolutions and skip connections from the encoder.
- **Output Layer**: A `1x1` convolution to generate the final depth map.

## Training
- **Loss Function**: Mean Squared Error (MSE)
- **Optimizer**: Adam
- **Device**: GPU (`cuda`) if available, else CPU
- **Epochs**: Adjustable based on dataset size and convergence

The training loop follows standard PyTorch best practices, including backpropagation and loss optimization.

## Evaluation
- The model is evaluated using MSE and visualized using Matplotlib.
- Predictions are compared against ground truth depth maps to assess accuracy.

## Applications
- **Autonomous Vehicles**: Helps in understanding depth for navigation.
- **Robotics**: Useful for object detection and grasping.
- **Medical Imaging**: Can be applied to 3D reconstruction from 2D images.
- **AR/VR**: Enhances scene understanding in virtual environments.

## Acknowledgments
- Built with PyTorch.

---
Feel free to contribute to this project! 🚀
