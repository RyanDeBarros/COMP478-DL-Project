COMP478-DL-Project

Term Project – COMP478: Deep Learning for Image Processing

## 📌 Project Title

Implementation of concepts from the paper:
“Learning RoI Transformer for Oriented Object Detection in Aerial Images”
by Jian Ding, Nan Xue, Yang Long, Gui-Song Xia, Qikai Lu (CVPR 2019).

Paper PDF (CVPR 2019)


## 👥 Team Members & Roles

Person A (Dataset & Evaluation Lead) – prepares datasets, splits, and evaluation metrics (IoU, mAP).

Person B (Baseline Detector Lead) – sets up baseline object detector (YOLO / Faster R-CNN / Light-Head R-CNN).

Person C (RoI Transformation Lead) – implements horizontal-to-rotated bounding box conversion and visualization.

Person D (Feature Extraction & Report Lead) – experiments on rotation-invariant features (HOG / CNN), creates plots & leads report writing.


## 📂 Repository Structure
'''
COMP478-DL-Project/
│── notebooks/ # Jupyter notebooks for experiments & demos
│ ├── features_rotation_test.ipynb
│
│── src/ # Source code for detectors, RoI transforms, etc.
│
│── data/ # (gitignored) Dataset storage (HRSC2016/DOTA subset)
│
│── docs/ # Documentation & report drafts
│ ├── report_outline.md
│
│── requirements.txt # Python dependencies
│── README.md # Project description & instructions
│── .gitignore
'''

## ⚙️ Setup Instructions
1. Clone the repository
git clone https://github.com/RyanDeBarros/COMP478-DL-Project.git
cd  .\COMP478-DL-Project\

2. Create and activate a conda environment
conda create -n roi-transformer python=3.9 -y
conda activate roi-transformer

3. Install the dependencies (required in order to run the project)
pip install -r requirements.txt


## 📊 Datasets
HRSC2016: High-Resolution Ship Collection (ships with oriented bounding boxes).

DOTA (subset): Dataset for Object Detection in Aerial Images (multi-class rotated objects).

(We will start with HRSC2016 due to smaller size and easier training.)


## 🚀 Project Goals

Implement and visualize Horizontal → Rotated RoI transformation.

Train/test a baseline detector (horizontal bboxes).

Extend to predict rotated bounding boxes.

Evaluate rotation-invariance of features (HOG / CNN).

Compare baseline vs rotated detectors.





