# CortexAI: Hybrid Ensemble Brain Tumor Detector 🧠

CortexAI is a deep learning-based desktop application designed to classify brain MRI images as either **Tumor** or **Healthy**. The project combines a **VGG16 transfer-learning model** with a custom **Hybrid CNN-Transformer model** using prediction-level ensemble learning.

The application includes a user-friendly graphical interface built with **Tkinter**, allowing users to upload an MRI image and receive a classification result with a confidence score.

> **Disclaimer:** This project is intended for educational and research purposes only. It is not a clinically validated medical diagnostic tool and should not be used as a substitute for professional medical diagnosis.

---

## 📸 Screenshots

![Application Screenshot 1](app_images/bt1.png)

![Application Screenshot 2](app_images/bt2.png)

![Application Screenshot 3](app_images/bt3.png)

---

## ✨ Features

- **MRI Image Upload:** Select a brain MRI image directly from your computer.
- **Binary Classification:** Classifies the uploaded image as **Tumor** or **Healthy**.
- **Confidence Score:** Displays the model's confidence for the prediction.
- **Ensemble Prediction:** Combines predictions from VGG16 and a Hybrid CNN-Transformer model.
- **Desktop GUI:** Provides an easy-to-use interface built with Python's Tkinter library.
- **Model Evaluation:** Includes classification metrics, confusion matrix analysis, and training-history visualization.

---

## 🤖 Models Used

### 1. VGG16 — Transfer Learning

The project uses a **VGG16-based convolutional neural network** with transfer learning. VGG16 provides pre-trained image feature extraction capabilities that are adapted for binary brain MRI classification.

**Observed Validation Accuracy:** approximately **98–99%**

### 2. Hybrid CNN-Transformer

The custom Hybrid CNN-Transformer architecture combines:

- **CNN layers** for extracting local spatial features such as edges and textures.
- **Transformer-based processing** for learning broader relationships between extracted features.

**Observed Validation Accuracy:** approximately **59.27%**

### 3. Ensemble Model

Predictions from the VGG16 and Hybrid CNN-Transformer models are averaged to generate the final classification:

```python
ensemble_preds_prob = (vgg_preds + hybrid_preds) / 2.0
