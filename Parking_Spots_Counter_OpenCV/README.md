# Parking Spots Counter — OpenCV & skimage

This project focuses on **counting available parking spots in a garage video** using computer vision.  
The goal was not just to detect occupied and empty spots, but to build a **real-time parking monitoring pipeline** that combines image processing, a pre-trained classifier, and performance optimizations.

This project represents the **first step of a larger system**, where the current pipeline serves as the foundation for the next stages.

## Demo

<p align="center">
  <img src="../assets/Parking_Spots_Counter_OpenCV/OpenCV_demo.gif" width="800"/>
</p>

<p align="center">
  Real-time parking spot detection using OpenCV and SVC classifier
</p>

<p align="center">
  <video src="../assets/Parking_Spots_Counter_OpenCV/OpenCV_vid_demo.mp4" controls width="800"></video>
</p>

---

## Project Objectives

- Detect and count **available parking spots** from an overhead garage video  
- Use a **pre-trained SVC classifier** to classify each parking spot as occupied or empty  
- Extract parking spot boundaries automatically from a mask  
- Visualize parking availability in real time using colored bounding boxes  
- Improve runtime performance for smoother real-time execution  

---

## Data Preparation Approach

The project uses three main inputs:

- A **garage video** recorded from above  
- A **binary mask** defining the parking spot regions  
- A **pre-trained classification model** (`model.p`)  

### Video Input

The main video is a continuous overhead recording of a parking lot.

Video path:
- `../assets/Parking_Spots_Counter_OpenCV/parking_Full_loop.mp4`

To make testing more reliable, the original short video was extended by **concatenating it with the same video in reverse**, giving the system more time to evaluate changing parking conditions.

---

### Parking Spot Definition

The parking boundaries were defined using a binary mask.

Instead of manually entering each spot coordinate, the project used:

- `cv2.connectedComponentsWithStats`

This allowed automatic extraction of connected parking regions and conversion into bounding boxes for every parking slot.

---

## Core Pipeline

### 1. Spot Extraction

Parking spots were extracted from the mask using connected components analysis.

A helper function was used to:
- read the connected components output
- retrieve the bounding box of each parking region
- store each parking slot as:
  - `x`
  - `y`
  - `width`
  - `height`

This created a clean list of all detectable parking spaces in the garage.

---

### 2. Spot Classification

Each parking spot crop was passed into a **pre-trained SVC classifier**.

The classification process included:
- resizing the cropped spot image to **15 × 15 × 3**
- flattening the image into a feature vector
- predicting whether the spot is:
  - **empty**
  - **not empty**

This was implemented through the `empty_or_not()` function.

---

### 3. Real-Time Optimization

A major part of the project was not just classification, but making the pipeline work more efficiently in real time.

#### First Optimization
Instead of classifying on **every frame**, the system performs classification every:

- **30 frames** (approximately once per second)

This reduces unnecessary repeated predictions.

#### Second Optimization
Since most parking spots do not change frequently, a second condition was added:

- compare the current crop with the previous frame crop
- compute the difference using the **mean pixel value**
- classify again **only if the change is large enough**

This was implemented through:

- `calc_diff(im1, im2)`

After analyzing the histogram of change values, the threshold was standardized and set to:

- **0.4**

This means a spot is only reclassified if its normalized change exceeds this threshold.

This significantly reduces unnecessary computations and improves runtime smoothness.

---

## Output Visualization

<p align="center">
  <img src="../assets/Parking_Spots_Counter_OpenCV/OpenCV_demo.gif" width="800"/>
</p>

<p align="center">
  Real-time parking spot detection using OpenCV and SVC classifier
</p>

Each parking spot is visualized directly on the video frame:

- **Green border** → available spot  
- **Red border** → occupied spot  

In addition, a summary box is displayed at the top of the frame showing:

- **Available spots / Total spots**

Example:
- `Available spots: 124 / 396`

This makes the result immediately readable and useful in a real parking monitoring setting.

---

## Model Evaluation & Practical Results

The project demonstrates that a relatively lightweight classification pipeline can be used to monitor parking availability effectively when combined with:

- automatic region extraction  
- selective frame processing  
- change-based reclassification  

The final result is not just a classifier, but a more complete **computer vision workflow** designed for practical use.

---

## Key Insights

- Parking spot detection becomes much more scalable when the slot regions are extracted automatically from a mask  
- Real-time systems require more than just model accuracy — runtime efficiency matters a lot  
- Running classification on every frame is often unnecessary in structured scenes like parking lots  
- Change-based reclassification is a strong optimization when objects remain stable across frames  
- Combining OpenCV image processing with a pre-trained classifier creates a practical and effective monitoring pipeline  

---

## Tools Used

- **Python**
  - numpy  
- **Computer Vision**
  - OpenCV (`cv2`)  
  - scikit-image (`skimage`)  
- **Model Inference**
  - pickle  
  - pre-trained SVC classifier  

---

## Dataset / Inputs

The project uses:

- Garage video feed  
- Binary parking mask  
- Pre-trained parking spot classifier  

[Assets](../assets/Parking_Spots_Counter_OpenCV)


Main file used in the notebook:
- `parking_Full_loop.mp4`

---

## Project Files

- Jupyter Notebook (`.ipynb`)  
- Video: [parking_Full_loop.mp4](../assets/Parking_Spots_Counter_OpenCV/parking_Full_loop.mp4)
- Mask: [mask_Full.png](../assets/Parking_Spots_Counter_OpenCV/mask_Full.png)  
- Pre-trained model: [model.p](../assets/Parking_Spots_Counter_OpenCV/model.p)  

---

## Author

**Adham Nassar**  
[LinkedIn](https://www.linkedin.com/in/adham-nassar-83ba54347)

This project demonstrates strong skills in **computer vision, image processing, real-time optimization, and practical ML deployment**, with a focus on building a structured and scalable parking monitoring pipeline.