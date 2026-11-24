# POTHOLE-DETECTION-CLASSIFICATION-and-YOLO-COMPARISON
# 🚧 Pothole Detection, Classification & YOLO Comparison

### AI-Driven Road Damage Detection Using Deep Learning and Computer Vision

## 📌 Project Overview

Potholes are a major road safety concern that can cause accidents, vehicle damage, and increased road maintenance costs. Traditional manual road inspection is time-consuming, expensive, and inefficient.

This project develops an AI-based pothole detection system using Deep Learning and Computer Vision. It compares different YOLO object detection models to identify and localize potholes in road images.

Three YOLO models were implemented and evaluated:

- YOLOv8n
- YOLOv8s
- YOLO11n

Additionally, image classification experiments were conducted using EfficientNet-B0, Simple CNN, and ResNet18.

The main focus of this project is object detection and performance comparison between YOLO models.

## 🎯 Project Objectives

- Develop an automated pothole detection system.
- Detect and localize potholes using bounding boxes.
- Compare YOLOv8n, YOLOv8s, and YOLO11n.
- Evaluate models using Precision, Recall, mAP50, and mAP50-95.
- Compare model size and inference speed.
- Explore image classification approaches using CNN architectures.
- Demonstrate pothole detection on new road images.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| PyTorch | Deep learning framework |
| YOLOv8 / YOLO11 | Object detection |
| EfficientNet-B0 | Image classification |
| ResNet18 | Image classification |
| CNN | Deep learning |
| OpenCV | Image processing |
| Scikit-learn | Dataset splitting and evaluation |
| Google Colab | Model training |
| Kaggle | Dataset source |

## 📂 Dataset

**Dataset:** [Pothole Detection Dataset – Kaggle](https://www.kaggle.com/datasets/rajdalsaniya/pothole-detection-dataset)

The dataset contains 2,083 road images with pothole bounding-box annotations.

### Dataset Information

| Property | Details |
|---|---|
| Total Images | 2,083 |
| Classes | 1 (Pothole) |
| Annotation Format | YOLO TXT |
| Training Images | 1,458 |
| Validation Images | 312 |
| Testing Images | 313 |

All images contain at least one annotated pothole.

## ⚙️ Methodology

The project follows an end-to-end deep learning workflow:

1. **Data Collection:** Downloaded the pothole dataset from Kaggle.
2. **Data Preprocessing:** Inspected images and validated YOLO bounding-box annotations.
3. **Dataset Splitting:** Divided the dataset into training, validation, and testing sets using random seed 42.
4. **Model Training:** Fine-tuned three pretrained YOLO models using identical training configurations.
5. **Model Evaluation:** Compared performance using standard object detection metrics.
6. **Inference:** Tested the selected model on a new road image.

## 🧠 Models Implemented

### 1. Image Classification

The following classification models were explored:

- EfficientNet-B0
- Simple CNN
- ResNet18

**Important Note:** The classification experiment has a dataset-labeling limitation. The folders named `train` and `valid` were interpreted as separate classes, rather than pothole and normal-road images. Therefore, the reported high classification accuracy does not represent actual pothole classification performance.

### 2. Object Detection

Three YOLO models were trained and compared:

- **YOLOv8n:** Lightweight nano model.
- **YOLOv8s:** Small model with a larger computational footprint.
- **YOLO11n:** Lightweight model from the newer YOLO architecture.

### Training Configuration

| Parameter | Value |
|---|---|
| Framework | Ultralytics |
| Input Image Size | 640 × 640 |
| Epochs | 50 |
| Batch Size | 16 |
| Optimizer | AdamW (Auto) |
| Learning Rate | 0.002 |
| Random Seed | 42 |
| Hardware | Tesla T4 GPU |
| Training Environment | Google Colab |

## 📊 Experimental Results – YOLO Comparison

The following table presents the held-out test results from the research paper.

| Model | Precision | Recall | mAP50 | mAP50-95 |
|---|---:|---:|---:|---:|
| YOLOv8n | 79.9% | 69.1% | 77.8% | 40.9% |
| YOLOv8s | **83.2%** | 68.0% | **79.2%** | 41.2% |
| YOLO11n | 74.9% | **71.6%** | 78.5% | **42.4%** |

### 🏆 Best Model: YOLO11n

YOLO11n was selected based on its highest mAP50-95 score of **42.4%** and highest recall of **71.6%**.

It also provides a smaller model size and lower computational requirements.

### Model Size and Performance

| Model | Parameters | GFLOPs | Weight Size |
|---|---:|---:|---:|
| YOLOv8n | 3.13M | 8.6 | 6.5 MB |
| YOLOv8s | 11.13M | 28.4 | 22.5 MB |
| YOLO11n | 2.60M | 6.4 | 5.5 MB |

YOLO11n provides a good balance between detection performance, model size, and computational efficiency.

## 🔍 Detection Demonstration

The selected YOLO11n model was tested on an external road image.

- Detected potholes: 3
- Confidence threshold: 0.25
- Detection confidence scores: 0.71, 0.75, and 0.83

The demonstration illustrates how the model identifies potholes and marks their locations using bounding boxes.

## ⚠️ Limitations

- The dataset contains only pothole images and does not include normal-road negative samples.
- The classification experiment cannot establish actual pothole-versus-normal classification performance.
- The random image-level split may contain augmented copies of similar photographs across different partitions.
- Results are based on a single training run with random seed 42.
- Real-world performance under different weather, lighting, and road conditions has not been established.
- CPU, mobile, and edge-device inference performance has not been evaluated.
- The project has not undergone real-world field validation.

## 🚀 Future Enhancements

- Add normal-road images and hard negative samples.
- Improve dataset quality using duplicate removal and location-based splitting.
- Train and evaluate models with multiple random seeds.
- Extend detection to cracks, patches, and other road damage.
- Integrate GPS tagging for pothole location tracking.
- Develop a mobile application for crowd-based pothole reporting.
- Implement real-time vehicle camera integration.
- Deploy the model on edge devices.
- Connect pothole detection results with road maintenance systems.

## 💻 Installation and Requirements

The experiments were conducted using Google Colab with a Tesla T4 GPU.

Install the main libraries using:

```bash
pip install ultralytics
pip install torch torchvision
pip install opencv-python
pip install scikit-learn
pip install kagglehub
```

For GPU training, use a compatible CUDA-enabled PyTorch environment.

## ▶️ Running the Project

1. Open the project notebook in Google Colab.
2. Download the Kaggle pothole dataset.
3. Prepare and validate the YOLO annotations.
4. Create the training, validation, and testing splits.
5. Train YOLOv8n, YOLOv8s, and YOLO11n.
6. Evaluate the trained models.
7. Compare their detection performance.
8. Run inference on a new road image using the selected YOLO11n model.

## 👨‍💻 Project Contributors

**Mohammad Ubaidullah**

**Anurodh Kumar**

School of Computer Science and Engineering  
SR University, Warangal, Telangana, India.

## 📚 References

- [Ultralytics YOLO Documentation](https://docs.ultralytics.com/)
- [Pothole Detection Dataset – Kaggle](https://www.kaggle.com/datasets/rajdalsaniya/pothole-detection-dataset)
- [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)
- [Scikit-learn Documentation](https://scikit-learn.org/)

---

## ⭐ Conclusion

This project demonstrates the application of Deep Learning and Computer Vision for automated pothole detection.

The experimental comparison shows that YOLO11n achieved the highest mAP50-95 score while maintaining a compact model size and computational efficiency.

The project provides a foundation for future intelligent road monitoring systems, real-time pothole detection, and automated road maintenance applications.

**If you find this project useful, consider giving this repository a ⭐ on GitHub!**
