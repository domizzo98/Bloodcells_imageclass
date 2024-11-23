# Blood Cell Classification with Computer Vision

This project aims to classify blood cell images with computer vision, achieving 97.2% accuracy using a simplified InceptionResNetV2 model. Through experimentation with neural networks and data processing, we identified the optimal architecture and techniques for this task.

![Alt text](images/images_example.png)

# Dataset

The dataset comprises 15,092 images of eight blood cell types. The size of the images is 48×48 pixels. Visual and statistical analysis revealed variability in cell dimensions and bimodal intensity distributions, likely due to differing imaging conditions.

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

The final model used for classification is a reduced **InceptionResNetV2** with three Inception ResNet Block A and one Reduction Block A, Batch Norm on standard layers, and residuals scaled by 0.1 for stability. RandomFlip is applied for data augmentation.

## References
[1] Sandler, M., Howard, A., Zhu, M., Zhmoginov, A., & Chen, L. C. (2018). Mobilenetv2: Inverted residuals and linear bottlenecks. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 4510-4520).
[2] He, K., Zhang, X., Ren, S., & Sun, J. (2016). Deep residual learning for image recognition. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 770-778).
[3] Huang, G., Liu, Z., Van Der Maaten, L., & Weinberger, K. Q. (2017). Densely connected convolutional networks. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 4700-4708).
[4] Dosovitskiy, A., Beyer, L., Kolesnikov, A., Weissenborn, D., Zhai, X., Unterthiner, T., ... & Houlsby, N. (2020). An image is worth 16x16 words: Transformers for image recognition at scale. arXiv preprint arXiv:2010.11929.
[5] Szegedy, C., Ioffe, S., Vanhoucke, V., & Alemi, A. (2017, February). Inception-v4, inception-resnet and the impact of residual connections on learning. In Proceedings of the AAAI conference on artificial intelligence (Vol. 31, No. 1).

