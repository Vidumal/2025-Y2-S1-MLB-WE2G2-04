# 😷 Face Mask Classifier – AI to the Rescue! 🦾

## 🚀 Project Mission
Hey there! Welcome to our **Face Mask Classifier** project.  
We built a smart AI to tell if someone’s wearing a mask or not 😷. Perfect for making the world a bit safer (and keeping your mom happy).  

---

## 🗂 Project Structure

"2025-Y2-S1-MLB-WE2G2-04/
│
├── README.md
├── data/
│ ├── raw/ # Original dataset(s)
│ └── external/ # Any bonus datasets
├── notebooks/
│ ├── ITxxxxxx_Preprocessing_technique.ipynb # Member magic notebooks
│ └── group_pipeline.ipynb # All preprocessing in one
└── results/
├── eda_visualizations/ # Pretty charts & plots
├── logs/ # Optional logs for debugging
└── outputs/ # Final processed dataset / features"

---

## 🖼 Dataset Details
- **Total Images**: ~2,000  
- **Classes**: `WithMask` vs `WithoutMask`  
- **Split**:  
  - Train: 1,600 (augmented to ~4,800 for AI to learn better)  
  - Validation: 200  
  - Test: 200  

*Fun fact:* Only the training set gets augmented. We don’t cheat with validation or test sets 😏.  

---

## 🔧 Preprocessing Pipeline
1. Remove corrupted & duplicate images 🗑️  
2. Resize all images to **224×224** 📏  
3. Convert BGR → RGB and normalize pixels 🎨  
4. Encode labels numerically (`WithMask=0`, `WithoutMask=1`)  
5. Shuffle dataset 🔀  
6. Split into Train / Validation / Test  
7. Augment training images (rotate, flip, zoom, brightness) ✨  

---

## 🧠 Model Overview
- Base: **MobileNetV2** (pre-trained on ImageNet)  
- Custom head:
  - GlobalAveragePooling  
  - Dense(128, ReLU) + Dropout(0.5)  
  - Dense(2, Softmax)  
- Loss: `categorical_crossentropy`  
- Optimizer: `Adam`  
- Metric: `Accuracy`  

---

## 🎯 How to Run (Install Dependencies)
1. **Clone the repo**:  
```bash
git clone https://github.com/GroupID/FaceMaskClassifier.git
cd FaceMaskClassifier
