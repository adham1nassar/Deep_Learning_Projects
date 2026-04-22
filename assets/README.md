# Assets Folder

This folder contains all the **datasets, images, videos, and supporting files** used in the deep learning and computer vision projects within this repository.

---

## Contents

- **Image datasets** – Raw image data organized into class-based folders for training deep learning models  
- **Videos & Media** – Input videos used for real-time computer vision tasks  
- **Visualizations & Plots** – Training results such as accuracy curves, sample grids, and model outputs  
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

- Input video:
  - `parking_Full_loop.mp4`  
  - `parking_crop_loop.mp4`  
- Processed demo:
  - `OpenCV_demo.gif`  
  - `OpenCV_vid_demo.mp4`  
- Parking masks:
  - `mask_Full.png`  
  - `mask_crop.png`  
- Pre-trained model:
  - `model.p`  

These assets support a **real-time parking spot detection system**, including:
- video-based input  
- region masking for parking slots  
- model inference outputs  
- final visualization (GIF + video)

---

## Related Projects

- [Flowers Recognition — CNN Image Classification](../Flowers_Recognition_CNN)  
- [Parking Spots Counter — OpenCV Real-Time Detection](../Parking_Spots_Counter_OpenCV)  

---

## Notes

- All assets are organized per project to maintain a **clean and modular structure**  
- Large media files (videos, GIFs) are included for **visual demonstration purposes**  
- This centralized structure ensures easy access and scalability for future projects  

---