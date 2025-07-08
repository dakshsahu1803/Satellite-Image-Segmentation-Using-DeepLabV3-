# 🛰️ Satellite Land Cover Segmentation using DeepLabV3+ & Google Earth Engine

This project focuses on semantic segmentation of satellite imagery to classify land cover types such as buildings, vegetation, roads, and water using **DeepLabV3+** with a **ResNet-101** backbone. The data is collected and preprocessed through **Google Earth Engine (GEE)** and integrated with **PyTorch** and **Albumentations** for model training and augmentation.

> 📍 Location Focus: **Prayagraj, India**  
> 📊 Achieved: **84% mIoU** (Mean Intersection over Union)

---

## 🌐 Objective

The goal is to build a robust, pixel-wise segmentation model to support:
- Urban planning
- Environmental monitoring
- Smart infrastructure development

---

## 📦 Dataset & Preprocessing

- **Source**: Landsat-8 Satellite Imagery via Google Earth Engine (GEE)
- **Region**: Rectangle bounding box over Prayagraj (Lat: 25.3–25.6, Lon: 81.8–82.0)
- **Classes**: Urban/Buildings, Vegetation, Roads, Water
- **Preprocessing**:
  - Mask creation with GEE
  - Data export and resizing
  - Label encoding and augmentation using Albumentations

---
## 🧰 Tech Stack

- **Deep Learning**: PyTorch, DeepLabV3+, ResNet-101
- **Data Handling**: OpenCV, NumPy, Rasterio
- **Augmentation**: Albumentations
- **Visualization**: Matplotlib, Pillow
- **Satellite Data**: Google Earth Engine (Python API), geemap

---
## 🛠️ Model Architecture
- Encoder: ResNet-101
- Decoder: ASPP + DeepLabV3+
- Optimizer: Adam
- Loss Function: BCE + Dice Loss
- Batch Size: 4
- Epochs: 25
---
## 📊 Results

| Metric         | Value     |
|----------------|-----------|
| mIoU (Mean IoU)| **84%**   |
| Accuracy       | 89%       |
| Dice Score     | 87%       |

---

## 🧪 Training Pipeline

```python
1. Authenticate & Initialize GEE
2. Define Area of Interest (AOI)
3. Export and Prepare Dataset
4. Apply Transformations (Albumentations)
5. Load Dataset into PyTorch Dataloader
6. Train DeepLabV3+ Model
7. Evaluate using mIoU, Accuracy
