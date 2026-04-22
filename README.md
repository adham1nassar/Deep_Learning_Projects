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

### Training Environment & Optimization

* Set up a full **TensorFlow GPU environment** using **WSL2** after encountering native Windows limitations  
* Resolved **CUDA / cuDNN runtime issues** by configuring `LD_LIBRARY_PATH` and linking required libraries  
* Enabled successful **GPU detection** on an **RTX 4060 Ti**  
* Achieved significantly faster model training compared to CPU execution  

---

## Tools & Techniques (across projects)

* **Python (NumPy, Pandas)**
* **Computer Vision (OpenCV, scikit-image)**
* **Deep Learning (TensorFlow, Keras)**
* **Image preprocessing & augmentation**
* **CNN architecture design**
* **Model inference & optimization**
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

This structure keeps the repository **clean, modular, and scalable**.

---

## Author

**Adham Nassar**  
[LinkedIn](https://www.linkedin.com/in/adham-nassar-83ba54347)

This repository showcases practical experience in **deep learning, computer vision, and real-time ML systems**, focusing on building complete, efficient, and scalable pipelines.