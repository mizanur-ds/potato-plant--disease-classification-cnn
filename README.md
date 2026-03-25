import os

# ---------- CHANGE THIS ----------
project_name = "Potato Plant Disease Classification using CNN"
github_username = "your-username"
dataset_link = "https://www.kaggle.com/datasets/arjuntejaswi/plant-village"
training_accuracy = "99.94%"
validation_accuracy = "98.96%"
test_accuracy = "98.44%"
confusion_matrix_image_path = "images/confusion_matrix.png"
# --------------------------------

class_names = ['Potato___Early_blight', 'Potato___Late_blight', 'Potato___healthy']

# Create README content
readme_content = f"""# 🥔 {project_name}

## 📌 Project Overview
This project uses a Convolutional Neural Network (CNN) to classify potato leaf diseases from images. 
The model can identify whether a leaf is affected by Early Blight, Late Blight, or is Healthy.
This type of system can help farmers detect plant diseases early and improve crop yield using AI-based solutions.

---

## 📊 Dataset
- Source: Kaggle PlantVillage Dataset  
- Link: {dataset_link}  

### Classes:
- {class_names[0]}  
- {class_names[1]}  
- {class_names[2]}  

---

## ⚙️ Data Preprocessing
- Images resized to a fixed size
- Normalization (pixel scaling: 0–1)
- Dataset split: 80% train / 10% val / 10% test
- Optimizations: caching, shuffling, prefetching

---

## 🔄 Data Augmentation
- Random Flip (horizontal & vertical)
- Random Rotation

---

## 🧠 Model Architecture
- Multiple Conv2D + MaxPooling layers
- Flatten + Dense layer
- Softmax output for 3 classes

---

## 🚀 Training Details
- Epochs: 40  
- Optimizer: Adam  
- Loss Function: SparseCategoricalCrossentropy  
- Hardware: GPU (tf.device("/GPU:0"))

---

## 📈 Results

| Metric | Value |
|------|------|
| Training Accuracy | {training_accuracy} |
| Validation Accuracy | {validation_accuracy} |
| Test Accuracy | {test_accuracy} |

---

## 📊 Model Evaluation

### 🔢 Confusion Matrix
![Confusion Matrix]({confusion_matrix_image_path})

### 📋 Classification Report

| Class | Precision | Recall | F1-Score | Support |
|------|----------|--------|---------|--------|
| {class_names[0]} | 0.97 | 1.00 | 0.99 | 134 |
| {class_names[1]} | 1.00 | 0.96 | 0.98 | 102 |
| {class_names[2]} | 1.00 | 1.00 | 1.00 | 20 |

### 📈 Overall Performance
- Accuracy: 98%
- Macro Avg F1-score: 0.99
- Weighted Avg F1-score: 0.98

### 🔍 Insights
- Model performs very well across all classes  
- Slight confusion between Early and Late Blight  
- Healthy leaves perfectly classified  

---

## ▶️ How to Run the Project

### 1. Clone Repository
```bash
git clone https://github.com/{github_username}/potato-disease-classification-cnn.git
cd potato-disease-classification-cnn
