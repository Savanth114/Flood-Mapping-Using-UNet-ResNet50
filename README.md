# Flood Extent Mapping Using a UNet–ResNet50 Hybrid Deep Learning Model

## Abstract

Accurate flood extent mapping is critical for disaster response, damage assessment, and environmental monitoring. Traditional flood detection techniques often struggle with complex terrain, vegetation, shadows, and varying illumination conditions. This project proposes a hybrid **UNet–ResNet50** deep learning architecture for semantic segmentation of flood-affected regions using synthetic flood imagery.

The model integrates a pre-trained ResNet50 encoder with a UNet decoder to leverage both deep feature extraction and precise spatial reconstruction. Experimental results demonstrate strong segmentation performance, achieving a **Test IoU of 0.8643**, **Dice Score of 0.86**, and **Pixel Accuracy of 0.86**, outperforming several baseline segmentation models.

---

# Project Overview

Floods are among the most devastating natural disasters worldwide, causing significant damage to infrastructure, agriculture, ecosystems, and human life. Rapid identification of inundated areas is essential for effective emergency response and recovery planning.

This project develops an automated flood extent mapping system using deep learning-based semantic segmentation. By combining the strengths of UNet and ResNet50, the proposed model accurately identifies flooded regions from aerial and satellite-like imagery.

---

# Model Architecture

The proposed architecture consists of:

### Encoder

* ResNet50 (Pre-trained on ImageNet)
* Deep feature extraction
* Residual learning
* Transfer learning capabilities

### Decoder

* UNet Decoder
* Progressive upsampling
* Skip connections
* Spatial information recovery

### Key Advantages

* Improved feature representation
* Better flood boundary detection
* Enhanced segmentation accuracy
* Strong generalization capability

<p align="center">
  <img src="https://github.com/user-attachments/assets/607e2b40-d661-447f-94d0-12baa4b27a7a" width="500">
</p>

<p align="center">
  <em>Figure 1. Proposed UNet–ResNet50 Architecture</em>
</p>

---

# Dataset

The model was trained using the **Synthetic Flood Imagery for Image Segmentation Dataset** available on Kaggle.

### Dataset Characteristics

| Feature         | Value               |
| --------------- | ------------------- |
| Total Images    | 3,050               |
| Image Type      | RGB                 |
| Resolution      | 512 × 512           |
| Mask Type       | Binary Segmentation |
| Flood Class     | 1                   |
| Non-Flood Class | 0                   |

### Dataset Split

| Dataset    | Percentage |
| ---------- | ---------- |
| Training   | 70%        |
| Validation | 15%        |
| Testing    | 15%        |

<h3 align="center">Sample Dataset Images</h3>

<p align="center">
  <img src="https://github.com/user-attachments/assets/54425a4c-7846-4439-846c-70cc33544b30" width="400">
</p>

<p align="center">
  <em>Examples from the Synthetic Flood Imagery for Image Segmentation dataset used for training and evaluation.</em>
</p>

---

# Data Preprocessing

The following preprocessing techniques were applied before model training:

* Image resizing to 512 × 512
* Pixel normalization
* Data augmentation
* Mask preprocessing
* Dataset balancing

## Data Augmentation Techniques

* Horizontal Flip
* Vertical Flip
* Random Rotation
* Brightness Adjustment
* Contrast Adjustment
* Gaussian Noise Injection
* Random Crop
* Zoom Transformation

These augmentations improve model robustness and reduce overfitting.

---

# Training Configuration

| Parameter     | Value                |
| ------------- | -------------------- |
| Batch Size    | 8                    |
| Epochs        | 30                   |
| Learning Rate | 1e-4                 |
| Loss Function | Binary Cross Entropy |
| Optimizer     | Adam                 |
| Input Size    | 512 × 512 × 3        |

---

# Technologies Used

### Programming Language

* Python

### Deep Learning Frameworks

* TensorFlow
* Keras

### Libraries

* NumPy
* OpenCV
* Matplotlib
* Scikit-Learn

### Development Environment

* Jupyter Notebook
* Google Colab

### Hardware

* NVIDIA Tesla T4 GPU
* Intel Xeon CPU
* 12–26 GB RAM

---

# Training Performance

## Accuracy Curve

<img width="728" height="474" alt="image" src="https://github.com/user-attachments/assets/e1d63d00-e1b3-40a9-b758-1a8b59b86087" />

## IoU Curve

<Figure size 800x500 with 1 Axes><img width="691" height="470" alt="image" src="https://github.com/user-attachments/assets/97c287ae-35ce-4c68-9a2e-b48fe89f3b9c" />


## Dice Coefficient Curve

Figure size 800x500 with 1 Axes><img width="691" height="470" alt="image" src="https://github.com/user-attachments/assets/e7df6d64-913e-43ea-a153-3d807bb9759a" />


## Loss Curve

<Figure size 800x500 with 1 Axes><img width="691" height="470" alt="image" src="https://github.com/user-attachments/assets/a8c32999-604c-4d02-838a-095d9aa5ecc0" />


The training results indicate stable convergence and strong validation performance throughout the training process.

---

# Evaluation Metrics

The model was evaluated using the following metrics:

### Intersection over Union (IoU)

Measures the overlap between predicted and ground truth flood masks.

### Dice Coefficient

Evaluates segmentation similarity and overlap quality.

### Pixel Accuracy

Measures the percentage of correctly classified pixels.

### Precision

Measures the correctness of predicted flood regions.

### Recall

Measures the model's ability to identify actual flooded areas.

### F1-Score

Harmonic mean of Precision and Recall.

---

# Experimental Results

## Proposed UNet–ResNet50 Performance

| Metric         | Score  |
| -------------- | ------ |
| Test IoU       | 0.8643 |
| Dice Score     | 0.86   |
| Pixel Accuracy | 0.86   |
| Precision      | 0.88   |
| Recall         | 0.85   |
| F1-Score       | 0.86   |

---

# Confusion Matrix

<Figure size 800x600 with 2 Axes><img width="631" height="547" alt="image" src="https://github.com/user-attachments/assets/2b387ee5-a2d5-4521-afca-6ee04e0d3fbd" />

### Classification Report

| Class     | Precision | Recall | F1-Score |
| --------- | --------- | ------ | -------- |
| Non-Flood | 0.88      | 0.87   | 0.88     |
| Flood     | 0.84      | 0.85   | 0.85     |

Overall Accuracy: **86%**

---

# Segmentation Results

<Figure size 1000x1500 with 15 Axes><img width="917" height="1490" alt="image" src="https://github.com/user-attachments/assets/7b41e8e9-3235-49ec-a456-f54512f9d0fd" />


The generated segmentation masks closely match the ground-truth flood regions, demonstrating the model's ability to accurately detect inundated areas.

---

# Comparative Analysis

| Model                    | IoU    |
| ------------------------ | ------ |
| FCN                      | 0.71   |
| UNet                     | 0.78   |
| DeepLabV3+               | 0.81   |
| VGG16-UNet               | 0.76   |
| UNet–ResNet50 (Proposed) | 0.8643 |

The proposed UNet–ResNet50 model achieved the highest segmentation performance among all evaluated architectures.

---

# Applications

* Flood Monitoring
* Disaster Response
* Emergency Planning
* Environmental Analysis
* Remote Sensing
* Water Resource Management
* Geospatial Intelligence

---

# Future Enhancements

* Real-world flood image evaluation
* Multi-temporal flood monitoring
* SAR imagery integration
* Transformer-based segmentation models
* Web deployment for real-time flood detection
* Edge AI deployment for field operations

---

# Repository Structure

```text
Flood-Mapping-Using-UNet-ResNet50/
│
├── Unet_Resnet50.ipynb
├── Flood_mapping_article_final.pdf
├── README.md
└── LICENSE
```

---

# Project Type

**Deep Learning Mini Project (Group Project)**

---

# Team Members

* Savanth G
* T Dhanush
* Posa Ajith Kumar
* Lokesh Gadhi

---

# Faculty Mentor

**Tintu Vijayan**
Assistant Professor
School of CSE & IS
Presidency University, Bengaluru, India

---

# Conclusion

This project demonstrates the effectiveness of a hybrid UNet–ResNet50 architecture for flood extent segmentation. By combining deep residual feature extraction with UNet's powerful decoder structure, the proposed model achieved superior performance compared to several baseline segmentation models. The results highlight the potential of deep learning-based flood mapping systems in supporting disaster management and environmental monitoring applications.

---

# License

This project is licensed under the MIT License.
