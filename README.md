# Deep Learning Projects — Main Features

This repo contains self-contained deep learning and computer vision projects (each in its own folder). Below are the **main features** covered in each project.

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

## Tools & Techniques (across projects)

* **Python (NumPy, Pandas)**
* **Computer Vision (OpenCV, scikit-image)**
* **Deep Learning (TensorFlow, Keras, YOLOv8)**
* **Object Tracking (SORT Algorithm)**
* **OCR (EasyOCR)**
* **Image preprocessing & augmentation**
* **CNN architecture design**
* **Real-time video processing**
* **Performance optimization techniques**
* **GPU acceleration (CUDA, cuDNN, WSL2)**
* **Visualization (matplotlib)**

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

This structure keeps the repository **clean, modular, and scalable**.

---

## Author

**Adham Nassar**  
https://www.linkedin.com/in/adham-nassar-83ba54347

This repository showcases practical experience in **deep learning, computer vision, and real-time ML systems**, focusing on building complete, efficient, and scalable pipelines.