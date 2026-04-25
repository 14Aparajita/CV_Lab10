# 🧠 Object Classification & Bounding Box Regression using VGG16

<p align="center">
  <img src="https://img.shields.io/badge/TensorFlow-Deep%20Learning-orange"/>
  <img src="https://img.shields.io/badge/OpenCV-Computer%20Vision-blue"/>
  <img src="https://img.shields.io/badge/Python-3.10-green"/>
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen"/>
</p>

---

## 📌 Project Overview

This repository presents a **multi-task deep learning model** that performs:

* ✅ Object Classification
* ✅ Bounding Box Regression (Localization)

The model is built using **VGG16 (Transfer Learning)** and trained on a custom dataset containing three object classes: **Butterfly, Dalmatian, and Dolphin**.

This project demonstrates how **classification + localization** can be solved simultaneously using a unified neural network architecture.

---

## 🎯 Objectives

* Build a CNN-based classification model
* Implement bounding box regression
* Use VGG16 as pretrained backbone
* Train a multi-output model in TensorFlow/Keras
* Evaluate performance using accuracy and MAE

---

## 📂 Dataset Structure

```
dataset/
 └── caltech101_classification/
      ├── butterfly/
      ├── dalmatian/
      ├── dolphin/
      ├── res_butterfly.txt
      ├── res_dalmatian.txt
      └── res_dolphin.txt
```

Each annotation file contains bounding box coordinates:

```
image_name, x1, y1, x2, y2
```

---

## 🧠 Model Architecture

### Backbone

* VGG16 (ImageNet pretrained)
* Fully Convolutional base (no top layers)

### Head Layers

* Global Average Pooling
* Dense (ReLU)
* Dropout

### Outputs

| Output Type | Activation | Task           |
| ----------- | ---------- | -------------- |
| Class       | Softmax    | Classification |
| BBox        | Sigmoid    | Regression     |

---

## ⚙️ Training Strategy

### Phase 1: Feature Extraction

* Freeze VGG16
* Train custom layers

### Phase 2: Fine-Tuning

* Unfreeze last layers of VGG16
* Train with lower learning rate

---

## 📊 Evaluation Metrics

* Classification Accuracy
* Bounding Box MAE (Mean Absolute Error)

---

## 📈 Results

| Metric              | Value  |
| ------------------- | ------ |
| Training Accuracy   | 100% |
| Validation Accuracy | 100% |
| Test Accuracy       | 100% |
| Test MAE            | 0.1065 |

---

## 🚀 How to Run

### 1. Clone Repo

```bash
git clone https://github.com/your-username/cv-lab10-vgg16.git
cd cv-lab10-vgg16
```

### 2. Install Requirements

```bash
pip install -r requirements.txt
```

### 3. Run Notebook

```bash
jupyter notebook notebook/CV_Lab10.ipynb
```

---

## 📦 Requirements

```
tensorflow
opencv-python
numpy
matplotlib
scikit-learn
```

---

## 💡 Key Highlights

* Multi-task learning (classification + localization)
* Transfer learning with VGG16
* Bounding box normalization & prediction
* Visualization of predictions
* End-to-end deep learning pipeline

---

## 🧾 Resume Value

> Built a VGG16-based multi-task computer vision model for object classification and bounding box regression using TensorFlow, incorporating transfer learning, fine-tuning, and prediction visualization.

---

## 🏁 Conclusion

This project successfully demonstrates how a single deep learning model can be used for both classification and localization tasks. Transfer learning significantly improves performance while reducing training time.

---

## 📚 References

* Simonyan, K., & Zisserman, A. “Very Deep Convolutional Networks for Large-Scale Image Recognition.” arXiv:1409.1556, 2014. This is the original VGG paper behind VGG16.
* Fei-Fei, L., Fergus, R., & Perona, P. “Learning Generative Visual Models from Few Training Examples: An Incremental Bayesian Approach Tested on 101 Object Categories.” CVPR Workshop / GMBV, 2004. This is the original Caltech-101 source.
* Girshick, R., Donahue, J., Darrell, T., & Malik, J. “Rich Feature Hierarchies for Accurate Object Detection and Semantic Segmentation.” arXiv:1311.2524, 2014. This is the original R-CNN paper and includes bounding-box regression for detection.
* Girshick, R. “Fast R-CNN.” arXiv:1504.08083, 2015. Useful background for object detection pipelines that combine classification and localization.
* TensorFlow Documentation. tf.keras.applications.VGG16 and tf.keras.applications.vgg16.preprocess_input. These are the official implementation references for the model backbone and preprocessing.
* Computer Vision Lab 10 handout, IIIT Naya Raipur. Experiment objective and dataset specification for VGG16-based class prediction and bounding-box regression.


---

## 👤 Author

Aparajita Vaish
M.Tech (ECE)
Computer Vision Laboratory

---

⭐ If you found this useful, consider giving a star!
