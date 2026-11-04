# 🚧 Road Damage Detection Using YOLO

## 📌 Project Overview

This project focuses on building an automated Road Damage Detection System using YOLO Object Detection models.

The system detects and classifies three types of road damage:
- **Pothole**
- **Crack**
- **Manhole**

Three YOLO models were trained and evaluated, followed by hyperparameter tuning to improve detection performance. The best-performing model was integrated into a Streamlit application for image-based road damage detection.

## 🎯 Project Objectives

- Detect different types of road damage using computer vision.
- Train and compare multiple YOLO architectures.
- Improve model performance through hyperparameter tuning.
- Evaluate models using Precision, Recall, mAP50, and mAP50-95.
- Develop an interactive Streamlit application.

## 📂 Dataset

**Source:** [Road Damage Dataset – Kaggle](https://www.kaggle.com/code/tareksabry/notebook04880d2fef)

- Total Images: 2,009
- Total Annotated Objects: 4,737
- Number of Classes: 3

### Class Distribution

| Class | Objects |
|---|---:|
| Pothole | 1,261 |
| Crack | 2,519 |
| Manhole | 957 |
| **Total** | **4,737** |

### Dataset Split

| Dataset | Images | Percentage |
|---|---:|---:|
| Training | 1,406 | 70% |
| Validation | 402 | 20% |
| Testing | 201 | 10% |

Random State: 42

## 🧠 Models Implemented

Three YOLO architectures were trained using the same dataset split.

- YOLOv8n
- YOLOv9t
- YOLO11n

### Baseline Model Comparison

| Model | Precision | Recall | mAP50 | mAP50-95 |
|---|---:|---:|---:|---:|
| YOLOv8n | 47.85% | 36.19% | 37.95% | 16.27% |
| YOLOv9t | 46.22% | 39.59% | 40.14% | 16.46% |
| YOLO11n | 43.70% | 40.99% | 38.20% | 16.84% |

## ⚙️ Hyperparameter Tuning

YOLOv9t was selected for further optimization through three experiments.

| Experiment | Image Size | Batch Size | Learning Rate |
|---|---:|---:|---:|
| Experiment 1 | 640 | 16 | 0.001 |
| Experiment 2 | 640 | 16 | 0.0005 |
| Experiment 3 | 800 | 8 | 0.0005 |

All experiments used:
- Epochs: 30
- Optimizer: AdamW
- Patience: 10

### Tuned YOLOv9t Results

| Experiment | Precision | Recall | mAP50 | mAP50-95 |
|---|---:|---:|---:|---:|
| Experiment 1 | 53.61% | 46.19% | 48.07% | 20.40% |
| Experiment 2 | 56.23% | 47.33% | 49.38% | 20.53% |
| Experiment 3 | 55.49% | 48.17% | 50.15% | 22.22% |

## 🏆 Final Model Selection

**Best Model: YOLOv9t – Experiment 3**

The third experiment achieved the highest Recall, mAP50, and mAP50-95 among the tuned experiments.

Final Test Performance:

- Precision: 55.49%
- Recall: 48.17%
- mAP50: 50.15%
- mAP50-95: 22.22%
- Model Size: 4.62 MB

## 🖥️ Streamlit Application

An interactive web application was developed using Streamlit.

### Application Features

- Upload road images.
- Detect potholes, cracks, and manholes.
- Display bounding boxes around detected objects.
- Show detection confidence.
- Display the total number of detected objects.

## 🛠️ Technologies Used

- Python
- YOLO (Ultralytics)
- PyTorch
- OpenCV
- Streamlit
- Pillow
- Kaggle
- Computer Vision
- Object Detection

## 📁 Project Structure

```text
Road_Damage_Detection/
│
├── app.py
├── best_road_damage_model.pt
├── notebook04880d2fef.ipynb
├── requirements.txt
└── README.md
```

## 🚀 Installation and Usage

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Navigate to the Project Folder

```bash
cd Road-Damage-Detection-YOLO
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Application

```bash
streamlit run app.py
```

The application will open in your browser at:

```text
http://localhost:8501
```

## 📊 Evaluation Metrics

- **Precision:** Measures how many predicted detections are correct.
- **Recall:** Measures how many actual objects were detected.
- **mAP50:** Mean Average Precision at IoU threshold 0.50.
- **mAP50-95:** Average mAP across IoU thresholds from 0.50 to 0.95.

## 🔮 Future Improvements

- Increase dataset size and diversity.
- Improve detection accuracy and localization.
- Address class imbalance.
- Experiment with additional YOLO architectures.
- Optimize inference speed.
- Deploy the application online.

## 👨‍💻 Author

**Tarek Sabry**

Data Science & AI | Computer Vision | Machine Learning

---

*This project was developed as part of a practical Data Science and Computer Vision learning journey.*
