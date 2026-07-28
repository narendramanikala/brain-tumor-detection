## 📂 Dataset

This project uses the **Brain MRI Images for Brain Tumor Detection** dataset from Kaggle.

### Dataset Information

- **Dataset Name:** Brain MRI Images for Brain Tumor Detection
- **Source:** https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection
- **Author:** Navoneel Chakrabarty
- **Task:** Binary Image Classification
- **Classes:**
  - `yes` – Brain MRI images with tumor
  - `no` – Brain MRI images without tumor
- **Image Size:** Resized to **224 × 224** pixels
- **Image Format:** JPG/PNG
- **Framework:** TensorFlow / Keras

## Dataset Preparation

The dataset is automatically downloaded using **KaggleHub**.

```python
import kagglehub

path = kagglehub.dataset_download(
    "navoneel/brain-mri-images-for-brain-tumor-detection"
)
```

The images are automatically divided into training and testing sets.

- **Training Set:** 80%
- **Testing Set:** 20%

## Folder Structure

```
dataset/
│
├── train/
│   ├── yes/
│   └── no/
│
└── test/
    ├── yes/
    └── no/
```

## Data Preprocessing

Before training, the following preprocessing steps are applied:

- Resize images to **224 × 224**
- Normalize pixel values to **[0,1]**
- Data augmentation:
  - Rotation (20°)
  - Zoom (20%)
  - Horizontal Flip
- Shuffle images before splitting

## Model

The project uses **ResNet50** (ImageNet pre-trained) with transfer learning.

- Pre-trained weights: ImageNet
- Global Average Pooling
- Dense (128 neurons, ReLU)
- Dropout (0.5)
- Sigmoid output layer for binary classification

## Evaluation Metrics

The trained model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Classification Report

## Citation

If you use this dataset, please cite:

```
@misc{brainmri2020,
  author = {Navoneel Chakrabarty},
  title = {Brain MRI Images for Brain Tumor Detection},
  year = {2020},
  publisher = {Kaggle},
  url = {https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection}
}
```
