# **SegFormer-FPN-Semantic-Segmentation**
### **Bridging Transformers & Pyramid Networks for Pixel-Level Understanding**

Hybrid **Vision Transformer + Enhanced FPN Decoder** using **SE-Block** and **CBAM Attention** for improved semantic segmentation on the **Pascal VOC** dataset.  
Includes baseline replication, architecture enhancements, performance comparison, and inference visualizations.

<img width="579" height="330" alt="image" src="https://github.com/user-attachments/assets/806718ff-d424-4f63-8b52-801e0fb53104" />

## Project Overview
Semantic segmentation assigns a **class label to every pixel**, enabling detailed scene understanding.

This project enhances the original **SegFormer** architecture by replacing its lightweight MLP decoder with an **Attention-Enhanced Feature Pyramid Network (FPN)** consisting of:

- **SE Block (Channel Attention)**
- **CBAM (Channel + Spatial Attention)**

These upgrades significantly improve segmentation quality, particularly for **small, thin, and complex objects**.

## 🎯 Motivation
SegFormer is a strong Transformer-based segmentation model, but its simple decoder limits fine-grained accuracy.

This project investigates whether adding a **multi-scale, CNN-based, attention-enhanced decoder** can:

✔ Improve feature fusion  
✔ Capture finer object boundaries  
✔ Boost segmentation metrics across classes  

##  Architecture Summary

<img width="773" height="321" alt="image" src="https://github.com/user-attachments/assets/f106c525-d444-401a-9837-a2659435e479" />

### 🔹 1. Encoder — SegFormer (Transformer Backbone)
- 4-stage hierarchical Transformer  
- Efficient self-attention  
- Overlapping patch embeddings  
- Multi-scale feature extraction  

### 🔹 2. Decoder — Enhanced Feature Pyramid Network (FPN)
- Lateral connections from all encoder stages  
- Top-down upsampling  
- 3×3 convolutional refinement  
- Multi-scale feature fusion  

### 🔹 3. Attention Modules

#### **SE Block (Channel Attention)**
- Global average pooling  
- FC → ReLU → FC → Sigmoid  
- Learns “important channels” dynamically  

#### **CBAM (Channel + Spatial Attention)**
- Adds spatial attention maps  
- Strengthens detection of small objects

<img width="338" height="476" alt="image" src="https://github.com/user-attachments/assets/cbe88bb5-12ae-4fd8-af25-51199efc2680" />

<img width="975" height="402" alt="image" src="https://github.com/user-attachments/assets/9e3b9538-e9be-4cb7-befd-b0751625b91e" />

## Results

### **Performance Comparison (ADE20K)**  
| Model | mIoU | mAcc | aAcc |
|-------|------|-------|-------|
| **SegFormer (Baseline)** | 64.88 | 80.05 | 90.83 |
| **SegFormer + FPN** | 65.63 | 75.46 | 91.50 |
| **SegFormer + FPN + SE + CBAM** | **67.19** | **76.74** | **92.08** |

<img width="909" height="490" alt="image" src="https://github.com/user-attachments/assets/a734373f-7b26-4363-b6f3-90fa0f5f72f3" />

<img width="974" height="322" alt="image" src="https://github.com/user-attachments/assets/cf7fca6e-05c7-4d34-99bf-7d8c6b621af7" />

### **Key Improvements**
✔ Higher mIoU and aAcc  
✔ Better small-object segmentation  
✔ More consistent predictions across categories  

## How to Use This Repository
Browse through `report.pdf` for complete methodology & results  


