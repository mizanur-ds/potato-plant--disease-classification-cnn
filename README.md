# 🥔 Potato Plant Disease Classification using CNN

## 📌 Project Overview
This project uses a Convolutional Neural Network (CNN) to classify potato leaf diseases from images. The model can identify whether a leaf is affected by **Early Blight**, **Late Blight**, or is **Healthy**.

This type of system can help farmers detect plant diseases early and improve crop yield using AI-based solutions.

---

## 📊 Dataset
- Source: Kaggle PlantVillage Dataset  
- Link: [PlantVillage Dataset](https://www.kaggle.com/datasets/arjuntejaswi/plant-village)

### Classes:
- Potato___Early_blight  
- Potato___Late_blight  
- Potato___healthy  

---

## ⚙️ Data Preprocessing
- Images resized to a fixed size
- Normalization (pixel scaling: 0–1)
- Dataset split:
  - Training: 80%
  - Validation: 10%
  - Test: 10%
- Performance optimizations:
  - Caching
  - Shuffling
  - Prefetching

---

## 🔄 Data Augmentation
To improve generalization and reduce overfitting:
- Random Flip (horizontal & vertical)
- Random Rotation

---

## 🧠 Model Architecture
A custom CNN model built using TensorFlow/Keras:

- Multiple Conv2D + MaxPooling layers
- Deep feature extraction (6 convolution blocks)
- Flatten layer
- Fully connected Dense layer
- Output layer (Softmax for 3 classes)

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
| Training Accuracy | 99.94% |
| Validation Accuracy | 98.96% |
| Test Accuracy | **98.44%** |

---

## 🔍 Sample Prediction

- Actual Label: Potato___Late_blight  
- Predicted Label: Potato___Late_blight ✅  

---

## 🧪 Model Evaluation
```python
scores = model.evaluate(test_ds)
print(f"Test Accuracy: {scores[1]*100:.2f}%")
