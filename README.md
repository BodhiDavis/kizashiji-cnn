# Japanese Character Recognition CNN

A Convolutional Neural Network for recognizing Kuzushiji (cursive Japanese) characters using the K49 and K-MNIST datasets.

## Overview

This project implements a CNN to classify handwritten Japanese characters from the [Kuzushiji dataset](https://www.kaggle.com/datasets/anokas/kuzushiji/data) available on Kaggle. The model can work with both:
- **K-MNIST**: 10 Hiragana characters (70,000 images)
- **K49**: 49 Hiragana characters (270,912 images)

## Dataset

The Kuzushiji dataset contains images of cursive Japanese characters (Kuzushiji) taken from historical documents. Kuzushiji was used for over 1000 years but is now unreadable to most modern Japanese speakers.

**Dataset Source:** https://www.kaggle.com/datasets/anokas/kuzushiji/data

### Dataset Files Used
- `k49-train-imgs.npz` - K49 training images (232,365 samples)
- `k49-train-labels.npz` - K49 training labels
- `k49-test-imgs.npz` - K49 test images (38,547 samples)
- `k49-test-labels.npz` - K49 test labels
- `k49_classmap.csv` - Class mapping for K49 characters
- KMNIST files (automatically downloaded via torchvision)

## Model Architecture

The CNN uses a simple architecture:

```
Input (1x64x64) 
    ↓
Conv2D(32 filters, 3x3, padding=1) → ReLU → MaxPool2D(2x2)
    ↓
Conv2D(64 filters, 3x3, padding=1) → ReLU → MaxPool2D(2x2)
    ↓
Flatten
    ↓
Linear(64*16*16 → 49)
    ↓
Output (49 classes)
```

```

## License

Dataset: See [Kuzushiji dataset license](https://www.kaggle.com/datasets/anokas/kuzushiji/data)

## References

- Clanuwat, T., Bober-Irizar, M., Kitamoto, A., Lamb, A., Yamamoto, K., & Ha, D. (2018). Deep Learning for Classical Japanese Literature. arXiv preprint arXiv:1812.01718.
- Dataset: https://www.kaggle.com/datasets/anokas/kuzushiji/data
