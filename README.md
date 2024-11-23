# Blood Cell Classification with Computer Vision

This project aims to classify blood cell images with computer vision, achieving 97.2% accuracy using a simplified InceptionResNetV2 model. Through experimentation with neural networks and data processing, we identified the optimal architecture and techniques for this task.

# Dataset

The dataset comprises 15,092 images of eight blood cell types. Visual and statistical analysis revealed variability in cell dimensions and bimodal intensity distributions, likely due to differing imaging conditions.

# Key Experiments

## Baseline

- MobileNetV2: Achieved 91.73% accuracy but exhibited unstable validation loss.

## Pretrained Models

- Fine-tuning **MobileNetV2** with ImageNet weights improved accuracy by 2.7% over baseline.

- **EfficientNetV2B0** showed instability, likely due to excessive complexity for the dataset.

## Architectures

- **ResNet-like**: Stable performance and validation loss.

- **DenseNet**: Inferior performance compared to ResNet.

- **Vision Transformer**: Stable but less effective.

- **InceptionResNetV2 (Simplified)**: Best performance at 97.2% accuracy.

## Final Model

The final optimal model used for classification is a reduced **InceptionResNetV2** with three Inception ResNet Block A and one Reduction Block A, Batch Norm on standard layers, and residuals scaled by 0.1 for stability. RandomFlip is applied for data augmentation.

