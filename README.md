# 🦵 Knee Osteoarthritis Severity Classification with Deep Learning 🧠

> **An AI-powered solution to automate knee osteoarthritis grading using X-ray images. Final ensemble model achieves 99.03% test accuracy.**

---

## 📌 Overview

Knee Osteoarthritis (KOA) is a progressive joint disease affecting millions globally. Manual radiographic grading is time-consuming and subjective. This project uses deep learning to automate the classification of KOA severity from X-ray images into five distinct grades:

- **Healthy**
- **Doubtful**
- **Minimal**
- **Moderate**
- **Severe**

We fine-tuned **four CNN models** and built an **ensemble architecture** to boost performance and reliability. This can act as a clinical decision support tool, especially in radiology-heavy environments.

---

## 📊 Model Highlights

| Model          | Accuracy   | Key Features                               |
| -------------- | ---------- | ------------------------------------------- |
| EfficientNetB5 | 94.14%     | Compound scaling, high parameter efficiency |
| InceptionV3    | 94.08%     | Multi-scale feature extraction              |
| MobileNet      | 93.65%     | Lightweight, fast inference                 |
| DenseNet       | 93.41%     | Feature reuse, gradient flow efficiency     |
| **Ensemble**   | **99.03%** | Softmax averaging of all four models        |

---

## 🧠 Ensemble Model Architecture

- **Inputs:** 224×224 RGB X-ray image
- **Backbones:** EfficientNetB5, DenseNet, InceptionV3, MobileNet
- **Output:** Averaged softmax across all models
- **Optimizer:** `Adamax (lr = 0.001)`
- **Loss:** `categorical_crossentropy`

---

## 📁 Dataset

**Source:** [Kaggle: Knee Osteoarthritis Dataset with Severity](https://www.kaggle.com/datasets/shashwatwork/knee-osteoarthritis-dataset-with-severity)

| Class     | Images |
|-----------|--------|
| Healthy   | 2286   |
| Doubtful  | 1046   |
| Minimal   | 1516   |
| Moderate  | 757    |
| Severe    | 173    |

- **Total Images:** 8,260
- **Image Size:** 224×224
- **Aspect Ratio:** 1.0
- **Splits:** Train (5778), Validation (826), Test (1656)

⚠️ *Data imbalance addressed using augmentation and relabeling techniques.*

---

## 📈 Performance Metrics

| Class    | Precision | Recall | F1-Score | Support |
|----------|-----------|--------|----------|---------|
| Healthy  | 1.0000    | 0.9993 | 0.9996   | 1382    |
| Moderate | 0.9520    | 0.9776 | 0.9646   | 223     |
| Severe   | 0.8913    | 0.8039 | 0.8454   | 51      |

- **Test Accuracy:** `99.03%`
- **Weighted F1 Score:** `~99.02%`
- **Confusion Matrix:** Clear distinction for Healthy and Moderate classes; minor confusion between Moderate and Severe.

