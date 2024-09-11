# MedFocusCLIP: Improving Few-Shot Classification in Medical Datasets

**MedFocusCLIP** leverages the Segment Anything Model 2 (SAM2) and CLIP (Contrastive Language-Image Pre-training) to improve few-shot classification on medical images such as X-rays, CT scans, and MRI scans. By combining segmentation with multimodal vision-language models, MedFocusCLIP enhances the model’s ability to identify critical regions in medical images with limited labeled data.

## Features
- **Few-Shot Learning**: Efficiently classifies medical images with minimal labeled data.
- **Advanced Segmentation**: Utilizes SAM2 to localize important regions in medical images.
- **Improved Accuracy**: Demonstrates higher performance than standard models across multiple medical datasets.

![Architecture](https://github.com/AADYA-ARORA/MedFocusClip/blob/main/image.png)

---

## 📊 Results

We evaluated MedFocusCLIP on multiple medical datasets, demonstrating significant improvements in accuracy for few-shot learning.

### 1. COVID-19 Dataset

| Model             | Accuracy (5% Data) | Accuracy (10% Data) | Accuracy (20% Data) | Accuracy (50% Data) | Accuracy (100% Data) |
|-------------------|--------------------|---------------------|---------------------|---------------------|----------------------|
| ResNet            | 51.52%             | 53.03%              | 62.12%              | 63.64%              | 80.30%               |
| Res2Net           | 43.94%             | 63.64%              | 68.18%              | 83.33%              | 83.33%               |
| VIT               | 65.15%             | 45.45%              | 60.61%              | 62.12%              | 65.15%               |
| Swin-Transformer  | 51.52%             | 62.12%              | 60.61%              | 78.79%              | 86.36%               |
| **MedFocusCLIP**  | **71.15%**         | **77.27%**          | **83.33%**          | **87.88%**          | **93.94%**           |

![COVID-19 Accuracy Graph](https://github.com/AADYA-ARORA/MedFocusClip/blob/main/covid.png)

---

### 2. Lung Disease Dataset

| Model             | Accuracy (5% Data) | Accuracy (10% Data) | Accuracy (20% Data) | Accuracy (50% Data) | Accuracy (100% Data) |
|-------------------|--------------------|---------------------|---------------------|---------------------|----------------------|
| ResNet            | 59.06%             | 69.23%              | 50.81%              | 77.83%              | 83.21%               |
| Res2Net           | 62.86%             | 66.62%              | 67.31%              | 67.16%              | 68.74%               |
| VIT               | 48.40%             | 47.51%              | 56.79%              | 57.04%              | 61.28%               |
| Swin-Transformer  | 75.56%             | 79.65%              | 81.48%              | 84.35%              | 85.68%               |
| **MedFocusCLIP**  | **81.28%**         | **82.12%**          | **84.49%**          | **85.63%**          | **91.52%**           |

![Lung Disease Accuracy Graph](https://github.com/AADYA-ARORA/MedFocusClip/blob/main/lungs.png)

---

### 3. Brain Tumor Dataset

| Model             | Accuracy (5% Data) | Accuracy (10% Data) | Accuracy (20% Data) | Accuracy (50% Data) | Accuracy (100% Data) |
|-------------------|--------------------|---------------------|---------------------|---------------------|----------------------|
| ResNet            | 68.50%             | 41.88%              | 77.19%              | 92.81%              | 93.75%               |
| Res2Net           | 70.63%             | 76.13%              | 79.18%              | 80.17%              | 81.31%               |
| VIT               | 61.48%             | 64.91%              | 64.99%              | 56.14%              | 66.59%               |
| Swin-Transformer  | 82.46%             | 86.65%              | 86.65%              | 88.94%              | 89.32%               |
| **MedFocusCLIP**  | **86.09%**         | **92.12%**          | **94.91%**          | **96.28%**          | **97.57%**           |

![Brain Tumor Accuracy Graph](https://github.com/AADYA-ARORA/MedFocusClip/blob/main/brain.png)

---

### 4. Breast Cancer Dataset

| Model             | Accuracy (5% Data) | Accuracy (10% Data) | Accuracy (20% Data) | Accuracy (50% Data) | Accuracy (100% Data) |
|-------------------|--------------------|---------------------|---------------------|---------------------|----------------------|
| ResNet            | 53.09%             | 59.28%              | 60.26%              | 62.87%              | 85.02%               |
| Res2Net           | 55.20%             | 61.45%              | 65.30%              | 70.85%              | 89.50%               |
| VIT               | 53.42%             | 57.00%              | 57.65%              | 57.98%              | 55.70%               |
| Swin-Transformer  | 67.43%             | 67.43%              | 70.68%              | 81.43%              | 78.50%               |
| **MedFocusCLIP**  | **58.63%**         | **69.06%**          | **76.22%**          | **97.39%**          | **96.09%**           |

![Breast Cancer Accuracy Graph](https://github.com/AADYA-ARORA/MedFocusClip/blob/main/breast.png)

---

## 🔬 Ablation Studies

### 1. Impact of Using Binary Masks
We evaluated the effect of using binary masks (black and white) versus segmented images. Using binary masks resulted in a significant performance drop, highlighting the importance of texture and color in medical image classification.

![Masked Images from Breast Cancer Dataset](https://github.com/AADYA-ARORA/MedFocusClip/blob/main/ABLATION_1%20(1).jpg)

In the figure, the left image is generated by SAM2, and the right image is generated by the SAM Adapter. The SAM2 mask significantly outperforms the SAM Adapter in terms of classification accuracy.

---

## 📁 Datasets
MedFocusCLIP has been evaluated on a variety of medical datasets:
- COVID-19 Dataset
- Lung Disease Dataset
- Brain Tumor Dataset
- Breast Cancer Dataset

---

## ⚙️ Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/MedFocusCLIP.git
   cd MedFocusCLIP
