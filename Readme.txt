# CASIA2 Image Forgery Detection  
### U-Net Segmentation with Noise Residual + Histogram Fusion  
**Author:** *Rehasun Tanjin Rony*  
**Course:** Digital Image Processing (GACS-7205)  
**Dataset:** CASIA v2  
**Model:** U-Net + Noise Residual + Histogram Fusion  
**Task:** Pixel-level forgery localization  
**Hardware:** CPU (Intel i5), 8 GB RAM  


## Raw Data Access
The dataset (3.31 GB) is stored on Google Drive because it is too large for GitHub.

🔗 Download the dataset here: 
 
https://drive.google.com/drive/folders/1Zlr0EGNlqdp1IvcgxbHo7VSU_e5d2Naf?usp=drive_link


---

## 📌 Project Overview

This project implements a **pixel-level forgery detection system** for the **CASIA v2** dataset using:

- **Noise Residual Maps (SRM filters)**
- **Histogram Inconsistency Maps (blockwise χ² distance)**
- **U-Net Segmentation Network**
- **BCE + Dice Loss (handles imbalance)**
- **40% / 15% / 15% dataset split** (for fast CPU training)

The model predicts **tampered regions** in manipulated images, generating a segmentation mask that highlights the manipulated areas.

This approach aligns with the research aim:

> *“Combining noise residual analysis with histogram-based inconsistencies improves the robustness and accuracy of image forgery detection.”*


---

## 📦 Installation

Install the required libraries:

```bash
pip install tensorflow numpy opencv-python matplotlib scikit-learn

Channel 1 → Red channel (normalized)
Channel 2 → SRM Noise Residual
Channel 3 → Histogram χ² Map


Training Instructions

Open the notebook:

unet_fusion_casia2.ipynb


Set dataset paths:

TP_DIR = r"...\CASIA2\Tp"
GT_DIR = r"...\CASIA2\CASIA 2 Groundtruth"


Run all cells.

Training uses 40% train, 15% validation, 15% test for speed.

📊 Results

Your evaluation prints something like:

Pixel Accuracy: 0.91+
IoU: 0.xx
Dice: 0.xx
Confusion Matrix:
[[TN FP]
 [FN TP]]


(Values depend on training duration.)

-----
Sample Output (Overlay)

The notebook automatically displays:

Original Image

Ground-truth Mask

Predicted Mask Overlay

Example (red = detected tampered region):

[VIS] Example 137:
(Visualization displayed)






