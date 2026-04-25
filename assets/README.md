# Assets Folder

This folder contains all the **datasets, images, and supporting files** used in the deep learning and computer vision projects within this repository.

---

## Contents

- **Image datasets** – Raw image data organized into class-based folders for training deep learning models  
- **Visualizations & Demos** – GIFs and plots used to demonstrate model performance  
- **Project-specific assets** – Each project has its own subfolder containing its data and outputs  

---

## Structure

The assets are organized into separate folders for each project:

---

### `Flowers_Recognition/`

- Flower image dataset (daisy, dandelion, rose, sunflower, tulip)  
- Training accuracy plots  
- Sample image visualizations  

---

### `Parking_Spots_Counter_OpenCV/`

- Demo:
  - `OpenCV_demo.gif`  
- Parking masks:
  - `mask_Full.png`  
  - `mask_crop.png`  
- Pre-trained model:
  - `model.p`  

These assets support a **real-time parking spot detection system**, including:
- region masking for parking slots  
- model inference outputs  
- final visualization (GIF demo)  

---

### `number_plate_recognition_Yolo_EasyOCR/`

- Dataset:
  - `License_Plate_Dataset/` (~10k labeled license plate images in YOLO format)  
- Demo:
  - `demo.gif`  

These assets support a **license plate recognition system**, including:
- vehicle and plate detection using YOLOv8  
- vehicle tracking using SORT  
- OCR processing using EasyOCR  
- final annotated output visualization  

---

## Related Projects

- [Flowers Recognition — CNN Image Classification](../Flowers_Recognition_CNN)  
- [Parking Spots Counter — OpenCV Real-Time Detection](../Parking_Spots_Counter_OpenCV)  
- [License Plate Recognition — YOLOv8, SORT & OCR](../number_plate_recognition_Yolo_EasyOCR)  

---

## Notes

- Large video files are intentionally excluded to keep the repository lightweight  
- GIFs are used instead for **fast, clear visual demonstrations**  
- Assets are organized per project to maintain a **clean and scalable structure**  

---