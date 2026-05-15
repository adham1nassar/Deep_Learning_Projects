# Flowers Recognition — CNN Image Classification

This project focuses on building a **Convolutional Neural Network (CNN)** to classify flower images into multiple categories.  
The goal was to create a complete **deep learning pipeline** from raw image folders to a trained model, while also setting up a fully optimized **GPU environment for efficient training**.

---

## Project Objectives

- Build a **multi-class image classification model**  
- Prepare image data from a **folder-based dataset**  
- Apply **data augmentation** for better generalization  
- Train a custom **CNN architecture** using TensorFlow / Keras  
- Evaluate model performance using training and validation metrics  

---

## Dataset

The dataset consists of images organized into class folders:

- `daisy`  
- `dandelion`  
- `rose`  
- `sunflower`  
- `tulip`  

Dataset path:
- `../assets/Flowers_Recognition`

---

## Data Visualization

### Sample Images from Dataset

<p align="center">
  <img src="../assets/Flowers_Recognition/train_gen.png" width="750"/>
</p>

This visualization shows a sample of images across different classes, highlighting variations in color, background, lighting, and angles that the model must learn to generalize.

---

## Data Preparation

### Data Cleaning

- Handled missing or corrupted images  
- Ensured correct label assignment from folder structure  

---

### Preprocessing & Transformation

- Resized all images to **224 × 224**  
- Normalized pixel values using `1./255`  
- Applied **feature scaling implicitly through normalization**  

---

### Data Augmentation

To improve model generalization:

- Rotation  
- Zoom  
- Width / height shift  
- Horizontal & vertical flipping  
- Shear transformation  

---

## Model Architecture

A custom **Convolutional Neural Network (CNN)** was built using TensorFlow / Keras.

### Key Components

- Conv2D layers for feature extraction  
- Batch Normalization for training stability  
- MaxPooling layers for dimensionality reduction  
- Dropout layers to reduce overfitting  
- GlobalAveragePooling2D  
- Dense layers for classification  
- Softmax output layer for multi-class prediction  

---

### Regularization

- Applied **Dropout layers**  
- Used **L2 regularization** to improve generalization  

---

## Model Training

### Configuration

- **Optimizer:** Adamax  
- **Loss Function:** Categorical Crossentropy  
- **Metric:** Accuracy  

### Training

- Trained for **30 epochs**  
- Used validation data to monitor generalization performance  

---

## Results & Model Performance

### Training vs Validation Accuracy

<p align="center">
  <img src="../assets/Flowers_Recognition/accuracy.png" width="750"/>
</p>

The model shows a steady improvement in both training and validation accuracy over epochs.

- Training accuracy increases consistently, indicating effective learning  
- Validation accuracy follows a similar trend, showing reasonable generalization  
- A small gap between training and validation suggests mild overfitting  

This confirms that the model successfully learned meaningful visual features from the dataset.

---

## Training Environment (GPU Setup)

A key part of this project was optimizing the deep learning environment:

- Set up a full **TensorFlow GPU environment** using **WSL2** after encountering native Windows limitations  
- Resolved **CUDA / cuDNN runtime issues** by configuring `LD_LIBRARY_PATH` and linking required libraries  
- Enabled successful **GPU detection** on an **RTX 4060 Ti**  
- Achieved significantly faster model training compared to CPU  

This highlights practical problem-solving beyond model building.

---

## Key Insights

- Image data requires strong preprocessing and augmentation for good performance  
- CNN architectures can effectively learn visual patterns from raw images  
- Regularization techniques improve model stability  
- GPU acceleration is critical for efficient deep learning workflows  
- Environment setup can be a major part of real-world ML projects  

---

## Tools Used

- **Python**
  - pandas, numpy  
- **Deep Learning**
  - TensorFlow  
  - Keras  
- **Image Processing**
  - ImageDataGenerator  
- **Visualization**
  - matplotlib  

---

## Project Files

- Jupyter Notebook (`.ipynb`)  
- [Dataset folder](../assets/Flowers_Recognition) 

---

## Author

**Adham Nassar**  
[LinkedIn](https://www.linkedin.com/in/adham-nassar-83ba54347)

This project demonstrates strong skills in **deep learning, CNN design, image preprocessing, and GPU environment setup**, with a focus on building efficient and scalable image classification pipelines.