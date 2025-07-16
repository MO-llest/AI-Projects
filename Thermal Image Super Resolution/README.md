## Thermal Image Super-Resolution

### Overview
This project explores deep learning-based techniques to enhance thermal image resolution for improved detection accuracy in autonomous and surveillance systems. Designed to operate under constrained hardware environments, this system integrates image super-resolution models and object detection pipelines to deliver high-quality thermal outputs.

---

### Datasets
- **KAIST** – RGB-Thermal image pairs focused on pedestrian detection.
- **FLIR ADAS** – Real-world thermal images for autonomous vehicle applications.

---

### Methodology

#### Image Degradation & Preprocessing
- Downscaled original images using OpenCV techniques to simulate low-resolution input.
- Focused on efficient processing using 128×128 and 256×256 image sizes.

#### Model Architectures
- **128×128 Models**: Lightweight custom SR architectures for low computing power.
  - **PSNR**: 28.87  
  - **SSIM**: 0.8087  
- **256×256 Models**: Trained using TF Dataset API for robust learning.
  - **PSNR**: 33.18  
  - **SSIM**: 0.8902  

#### Object Detection
- Applied pretrained **YOLOv8** on SR outputs from the 256×256 pipeline.
- Future direction includes fine-tuning YOLOv8 on:
  - Thermal images (from FLIR ADAS)
  - RGB images for comparative detection accuracy.

---

### Results Snapshot

| Model Input | Avg. PSNR | Avg. SSIM |
|-------------|-----------|-----------|
| 128×128     | 28.87     | 0.8087    |
| 256×256     | 33.18     | 0.8902    |

---

### Future Work
- Fine-tune YOLOv8 for FLIR ADAS thermal and RGB modalities.
- Explore hybrid RGB-guided SR approaches for resolution consistency.
- Evaluate detection accuracy gain using super-resolved inputs.

---

### Technologies Used
- OpenCV  
- TensorFlow  
- ESRGAN / SwinIR / CNN  
- YOLOv8  
