# 🩺 Skin Disease Classification Using Custom CNN

## 📌 Project Overview
This project implements a **Convolutional Neural Network (CNN)** from scratch to classify **skin disease images** into multiple categories using dermoscopic images. The model is trained using TensorFlow and Keras and evaluated using accuracy, precision, recall, F1-score, and confusion matrix.

The system also supports **real-time image prediction** by uploading a skin image.

---

## 🎯 Objectives
- Classify skin images into multiple disease classes
- Train a CNN model from scratch
- Evaluate performance using standard classification metrics
- Predict skin disease for a newly uploaded image

---

## 📂 Dataset Structure
The dataset is organized into three folders:
skin_data_split/
├── train/
├── val/
└── test/

- Images are RGB and resized to **96 × 96**
- Dataset contains **10 skin disease classes**
- Class imbalance is addressed using **balanced class weights**

### 🧪 Classes:
['acne', 'akiec', 'bags', 'bcc', 'bkl', 'df', 'mel', 'nv', 'redness', 'vasc']

---

## 🧠 Model Architecture
The model is a **custom CNN** built using the Keras Sequential API.

### 🔹 Convolutional Layers
- Conv2D (32 filters) + Batch Normalization + Max Pooling + Dropout
- Conv2D (64 filters × 2) + Batch Normalization + Max Pooling + Dropout
- Conv2D (128 filters × 2) + Batch Normalization + Max Pooling + Dropout

### 🔹 Fully Connected Layers
- Flatten
- Dense (1024 units, ReLU)
- Batch Normalization
- Dropout (0.5)
- Dense (Softmax output layer)

---

## ⚙️ Training Configuration
- **Optimizer**: Adam  
- **Learning Rate**: 0.001  
- **Loss Function**: Categorical Crossentropy  
- **Epochs**: Up to 150  
- **Callbacks**:
  - Early Stopping
  - Model Checkpoint  
- **Class Weights**: Applied to handle dataset imbalance  

---

## 📊 Model Performance (Test Set)
- **Accuracy**: ~72%
- **Weighted Precision**: ~71%
- **Weighted Recall**: ~72%
- Model performs strongly on majority classes (e.g., *nevus*)
- Performance on minority classes is limited due to fewer samples

---

## 📈 Evaluation & Visualization
- Classification Report (Precision, Recall, F1-score)
- Confusion Matrix (Heatmap)
- Training vs Validation Accuracy plot
- Training vs Validation Loss plot

---

## 🖼️ Image Prediction
The model supports real-time prediction for uploaded images:
1. Upload an image using Google Colab
2. Image is resized and normalized
3. Model predicts the skin disease class
4. Output displays predicted class label

---

## 💾 Saved Model
The best trained model is saved as:
saved_models/best_cnn_model.h5

---

## 🚀 Future Improvements
- Add data augmentation to reduce overfitting
- Improve minority class performance
- Use transfer learning models like VGG19 or MobileNet
- Increase image resolution for better feature extraction
- Deploy the model as a web or mobile application

---

## 🏁 Conclusion
This project demonstrates the effectiveness of a **custom CNN architecture** for multi-class skin disease classification. While the model achieves reasonable accuracy, further enhancements such as data augmentation and transfer learning can significantly improve performance and real-world usability.
