##Blood Cell Classification with Computer Vision

Introduction

This project aims to classify blood cell images with computer vision, achieving 97.2% accuracy using a simplified InceptionResNetV2 model. Through experimentation with neural networks and data processing, we identified the optimal architecture and techniques for this task.

Dataset

Size: 15,092 images of eight blood cell types.

Balance: Classes are nearly even.

Insights: Visual and statistical analysis revealed variability in cell dimensions and bimodal intensity distributions, likely due to differing imaging conditions.

Key Experiments

Baseline

MobileNetV2: Achieved 91.73% accuracy but exhibited unstable validation loss.

Pretrained Models

Fine-tuning MobileNetV2 with ImageNet weights improved accuracy by 2.7% over baseline.

EfficientNetV2B0 showed instability, likely due to excessive complexity for the dataset.

Data Augmentation

Tested RandomFlip, Translation, Rotation, Brightness, and Contrast.

Optimal set: RandomFlip, RandomTranslation, RandomRotation, significantly enhancing performance.

Simplified Architectures

ResNet-like: Stable performance and validation loss.

DenseNet: Inferior to ResNet.

Vision Transformer: Stable but less effective.

InceptionResNetV2 (Simplified): Best performance at 97.2% accuracy.

Final Model

A reduced InceptionResNetV2 with three Inception ResNet Block A and one Reduction Block A. Key features:

Batch normalization on standard layers.

Residuals scaled by 0.1 for stability.

Augmentation: RandomFlip provided optimal results.

Applications: Bounding box isolation, cell counting, and cytological analysis.

Conclusions

Optimal models depend on dataset size and characteristics.

Simpler architectures can outperform complex ones on smaller datasets.

Data augmentation is crucial for limited data.

Next Steps

For production, distill the model into a smaller architecture (e.g., ResNet) to improve speed and efficiency.

References

MobileNetV2: Sandler et al.

ResNet: He et al.

DenseNet: Huang et al.

Vision Transformer: Dosovitskiy et al.

InceptionResNetV2: Szegedy et al.

This README summarizes the project’s objectives, methods, and findings. For implementation details, refer to the project notebook.
