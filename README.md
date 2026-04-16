# Deep Learning Projects — Main Features

This repo contains self-contained deep learning projects (each in its own folder). Below are the **main features** covered in each project.

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

### Training Environment & Optimization

* Set up a full **TensorFlow GPU environment** using **WSL2** after encountering native Windows limitations  
* Resolved **CUDA / cuDNN runtime issues** by configuring `LD_LIBRARY_PATH` and linking required libraries  
* Enabled successful **GPU detection** on an **RTX 4060 Ti**  
* Achieved significantly faster model training compared to CPU execution  

---

## Tools & Techniques (across projects)

* **Python (NumPy, Pandas)**
* **Deep Learning (TensorFlow, Keras)**
* **Image preprocessing & augmentation**
* **CNN architecture design**
* **Model training & evaluation**
* **Regularization techniques (Dropout, L2)**
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
    - `assets/Flowers_Recognition/` → dataset and plots for the CNN project  

This structure keeps the repository **clean, modular, and scalable**.

---

## Author

**Adham Nassar**  
[LinkedIn](https://www.linkedin.com/in/adham-nassar-83ba54347)

This repository showcases practical experience in **deep learning, computer vision, and GPU-accelerated model training**, focusing on building complete and efficient neural network pipelines.