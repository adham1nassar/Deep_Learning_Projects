# License Plate Recognition — YOLOv8, SORT & EasyOCR

This project focuses on building a complete **license plate recognition system from video**, combining detection, tracking, OCR, and post-processing into one pipeline.

The goal was not just to detect license plates, but to create a system that can track vehicles, detect plates, read numbers, handle missing data, and produce a clean final output.

This project represents **part 2 of a 3-step system**, building on the previous parking detection project and leading into a final combined system.

---

## Demo

<p align="center">
  <img src="../assets/number_plate_recognition_Yolo_EasyOCR/demo.gif" width="800"/>
</p>

<p align="center">
  Vehicle tracking and license plate recognition using YOLOv8, SORT, and EasyOCR
</p>

---

## Project Overview

- Detected vehicles using YOLOv8  
- Trained a custom YOLO model for license plate detection  
- Tracked vehicles across frames using SORT  
- Matched each license plate to its corresponding vehicle  
- Extracted and preprocessed plate images  
- Read plate text using EasyOCR  
- Applied custom corrections to improve OCR accuracy  
- Stored results and handled missing detections  
- Generated a final clean annotated output  

---

## How It Works

The pipeline combines multiple components:

- **Detection:** YOLO identifies vehicles and license plates  
- **Tracking:** SORT assigns a consistent ID to each vehicle across frames  
- **Matching:** Plates are linked to vehicles based on position  
- **OCR:** EasyOCR reads plate numbers  
- **Post-processing:** Incorrect characters are corrected using custom rules  
- **Smoothing:** Missing detections are filled using interpolation  

This transforms frame-by-frame detection into a **stable and usable system**.

---

## Key Insights

- Detection alone is not enough — tracking is essential  
- OCR requires post-processing to be reliable  
- Real-world systems need data correction and smoothing  
- Combining multiple techniques creates a much stronger pipeline  

---

## Tools Used

- Python  
- OpenCV  
- YOLOv8 (Ultralytics)  
- EasyOCR  
- SORT Tracker  
- NumPy / Pandas  

---

## Project Structure

- Notebook for the full pipeline  
- SORT tracker file  
- CSV files for raw and fixed results  
- [Assets folder](../assets/number_plate_recognition_Yolo_EasyOCR) containing dataset and demo GIF  

---

## Final Note

This project is not just about detection — it’s about building a **complete computer vision system** that detects, tracks, reads, cleans, and visualizes data in a structured way.

---

## Author

Adham Nassar  
[linkedin](https://www.linkedin.com/in/adham-nassar-83ba54347)