# Deep Learning Projects — Main Features

This repo contains self-contained deep learning, computer vision, and NLP projects (each in its own folder). Below are the **main features** covered in each project.

---

## 1) Flowers Recognition — CNN Image Classification [🔗](/Flowers_Recognition_CNN)

* Built a **multi-class image classification model** using Convolutional Neural Networks (CNNs).
* Processed a **folder-based image dataset** with multiple flower categories:
  * Daisy
  * Dandelion
  * Rose
  * Sunflower
  * Tulip
* Applied **image preprocessing and normalization** to prepare data for training.
* Used **data augmentation techniques** to improve generalization:
  * Rotation, zoom, shifting, flipping, and shear transformations
* Designed a custom **CNN architecture** including:
  * Convolutional layers
  * Batch normalization
  * MaxPooling
  * Dropout
  * Dense layers with softmax output
* Trained the model using:
  * Adamax optimizer
  * Categorical crossentropy loss
* Evaluated performance using **training and validation accuracy trends**.
* Visualized model learning behavior through **accuracy plots**.
* Implemented **regularization techniques** to reduce overfitting.

---

## 2) Parking Spots Counter — Real-Time Computer Vision [🔗](/Parking_Spots_Counter_OpenCV)

* Built a **real-time parking monitoring system** using OpenCV and image processing techniques.
* Processed a **video feed from an overhead camera** to analyze parking availability.
* Defined parking regions using a **binary mask** and extracted spots automatically with:
  * `cv2.connectedComponentsWithStats`
* Applied a **pre-trained SVC classifier** to determine whether each parking spot is:
  * Occupied
  * Available
* Implemented a full pipeline:
  * Crop each parking spot
  * Resize and preprocess input
  * Classify using the trained model
* Visualized results directly on the video:
  * **Green boxes → available spots**
  * **Red boxes → occupied spots**
* Displayed a real-time counter:
  * `Available spots / Total spots`

---

### Real-Time Optimization & Performance

* Optimized performance by reducing unnecessary computations:
  * Ran classification every **30 frames (~1 second)** instead of every frame
* Introduced **change detection**:
  * Compared current and previous frames using mean pixel difference
  * Reclassified only when significant change occurs
* Determined threshold using histogram analysis:
  * Standardized threshold ≈ **0.4**
* Improved runtime efficiency and achieved smoother real-time performance

---

### Practical Enhancements

* Extended short video by **concatenating forward + reversed sequence** for better testing
* Built a structured pipeline combining:
  * Image processing
  * Feature extraction
  * Model inference
* Designed the system as the **first step of a larger parking analysis project**

---

## 3) License Plate Recognition — Detection, Tracking & OCR [🔗](/number_plate_recognition_Yolo_EasyOCR)

* Built a **complete license plate recognition pipeline** combining detection, tracking, and OCR.
* Trained a custom **YOLOv8 model** for license plate detection using a dataset of ~10,000 labeled images.
* Used a pre-trained YOLO model to detect vehicles in each frame.
* Implemented **SORT (Simple Online Realtime Tracking)** to:
  * Track vehicles across frames
  * Assign a consistent ID to each vehicle
* Matched each detected license plate to its corresponding tracked vehicle.
* Extracted and preprocessed license plate images:
  * Grayscale conversion
  * Thresholding for better OCR readability
* Used **EasyOCR** to read license plate text.
* Applied custom **post-processing rules** to fix OCR errors:
  * Character-to-number corrections (e.g., O → 0, S → 5)
* Stored results in structured CSV files:
  * Raw detections (`plate_info.csv`)
  * Fixed and interpolated results (`plate_info_fixed.csv`)
* Handled missing detections by:
  * Interpolating bounding boxes across frames
  * Smoothing tracking results
* Generated a final annotated output showing:
  * Vehicle tracking
  * License plate detection
  * Recognized license numbers

---

### System Design Insights

* Detection alone is not sufficient → **tracking is required for temporal consistency**
* OCR outputs require **post-processing and validation**
* Real-world pipelines need **data correction and interpolation**
* Combining detection + tracking + OCR creates a **complete intelligent system**

---

## 4) Emotion Classification using Word2Vec Embeddings & Deep Learning [🔗](/Emotion_Classification_Word2Vec_Embeddings_NLP)

A Natural Language Processing (NLP) project focused on multi-class emotion classification using both traditional machine learning models and deep learning.

The project uses custom Word2Vec embeddings to transform text into semantic vector representations before comparing multiple classification approaches including Logistic Regression, SVM, Random Forest, and a Neural Network built with TensorFlow/Keras.

### Key Features

* NLP preprocessing pipeline
* Custom Word2Vec embeddings (Skip-Gram)
* Sentence vector generation
* Multi-model comparison
* Deep learning for text classification
* Accuracy & weighted F1-score evaluation

---

## 5) Human Action Classification — ResNet18 Transfer Learning with PyTorch [🔗](/Human_Action_Classification_ResNet18_Transfer_Learning_PyTorch)

A computer vision project focused on **human action classification using PyTorch and transfer learning with an ImageNet-pretrained ResNet18**.

The project compares two different transfer-learning strategies: **full fine-tuning**, where the entire pretrained network is adapted to the new dataset, and **feature extraction**, where the ResNet18 backbone is frozen and only the final classification layer is trained.

### Key Features

* Image classification using **PyTorch**
* ImageNet-pretrained **ResNet18**
* Transfer learning for human action recognition
* Full network fine-tuning
* Frozen-backbone feature extraction
* Image preprocessing, normalization & augmentation
* Custom PyTorch training and evaluation loops
* Cross-Entropy Loss & Adam optimization
* `ReduceLROnPlateau` learning-rate scheduling
* GPU-accelerated training with CUDA
* Single-image inference
* Multiclass confusion matrix evaluation
* Comparison of two transfer-learning strategies

---

## Tools & Techniques (across projects)

* **Python (NumPy, Pandas)**
* **Machine Learning (Scikit-learn)**
* **Natural Language Processing (NLP)**
* **Word Embeddings (Word2Vec / Gensim)**
* **Computer Vision (OpenCV, scikit-image, Torchvision)**
* **Deep Learning (TensorFlow, Keras, PyTorch, YOLOv8)**
* **Transfer Learning (ResNet18)**
* **Object Tracking (SORT Algorithm)**
* **OCR (EasyOCR)**
* **Image preprocessing & augmentation**
* **CNN architecture design**
* **Text preprocessing & tokenization**
* **Custom training & evaluation loops**
* **Real-time video processing**
* **Performance optimization techniques**
* **GPU acceleration (CUDA, cuDNN, WSL2)**
* **Model evaluation (Confusion Matrices, Accuracy, F1-Score)**
* **Visualization (Matplotlib, Seaborn)**

---

## Repository Structure

The repository is organized as follows:

- Each project has its own folder containing:
  - Jupyter Notebook (`.ipynb`)
  - Project-specific code and results

- A single shared `assets/` folder contains all datasets and visualizations:
  - Each project has its own subfolder inside `assets/`
  - Example:
    - `assets/Flowers_Recognition/`
    - `assets/Parking_Spots_Counter_OpenCV/`
    - `assets/number_plate_recognition_Yolo_EasyOCR/`
    - `assets/Emotion_Word2Vec_NLP/`

This structure keeps the repository **clean, modular, and scalable**.

---

## Author

**Adham Nassar**

[LinkedIn](https://www.linkedin.com/in/adham1nassar)

This repository showcases practical experience in **deep learning, computer vision, NLP, transfer learning, and real-time ML systems**, focusing on building complete, efficient, and scalable machine learning pipelines.