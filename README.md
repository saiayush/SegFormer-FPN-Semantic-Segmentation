# SegFormer-FPN-Semantic-Segmentation
### *Bridging Transformers & Pyramid Networks for Pixel-Level Understanding*
Hybrid Vision Transformer + Enhanced Feature Pyramid Network with SE-Block &amp; CBAM attention for improved pixel-wise segmentation on the ADE20K dataset. Includes baseline replication, architecture modifications, performance comparison, and inference visualizations.


## Project Overview

Semantic segmentation assigns a class label to every pixel in an image, enabling machines to interpret scenes with fine detail.  
This project enhances the popular **SegFormer** architecture by replacing its lightweight MLP decoder with an improved **Feature Pyramid Network (FPN)** enriched with:

- **SE Block (Channel Attention)**  
- **CBAM (Convolutional Block Attention Module – Spatial + Channel Attention)**  

The result is a **significant improvement in accuracy**, especially for **small, thin, and complex objects**, where the baseline SegFormer struggles.


## 🧩 Motivation

Transformers have revolutionized computer vision with their ability to capture long-range dependencies.  
SegFormer is a strong baseline—but its simple decoder limits fine-grained segmentation quality.

This project explores whether adding a **CNN-based, multi-scale, attention-enhanced decoder** can:

✔ Improve feature fusion  
✔ Capture finer details  
✔ Boost segmentation metrics across classes  

## Architecture Summary

### 🔹 **Encoder – SegFormer (Transformer Backbone)**  
- Hierarchical 4-stage Transformer  
- Efficient self-attention  
- Patch embeddings (stride 4, patch size 7)  
- Multi-scale feature extraction  

### 🔹 **Decoder – Enhanced FPN**
- Lateral connections  
- Top-down upsampling  
- Multi-resolution feature fusion  
- 3×3 refinement convolutions  

### 🔹 **Attention Enhancements**
#### **SE-Block (Channel Attention)**
- Global average pooling  
- FC → ReLU → FC → Sigmoid  
- Learns “important channels” per stage  

#### **CBAM (Spatial + Channel Attention)**
- Highlights important spatial locations  
- Boosts segmentation of small objects  

## Results

### **Performance Metrics**

| Model | mIoU | mAcc | aAcc |
|-------|------|-------|--------|
| **SegFormer (Baseline)** | 64.88 | 80.05 | 90.83 |
| **SegFormer + FPN** | 65.63 | 75.46 | 91.50 |
| **SegFormer + FPN + SE + CBAM** | **67.19** | **76.74** | **92.08** |

✔ Improved class-level performance  
✔ Better segmentation of smaller objects like chairs, tables  
✔ Better overall consistency

