COMP478-DL-Project

Term Project – COMP478: Deep Learning for Image Processing

## 📌 Object Detection for Aerial Images Using the RoI Transformer: A PyTorch Reproduction and Multi-Dataset Evaluation

Implementation of concepts from the paper:
“Learning RoI Transformer for Oriented Object Detection in Aerial Images”
by Jian Ding, Nan Xue, Yang Long, Gui-Song Xia, Qikai Lu (CVPR 2019).

Paper PDF (CVPR 2019)


## 📂 Repository Structure
```
COMP478-DL-Project/
│── notebooks/ # Jupyter notebooks for experiments & demos
│ ├── RRoITransformerImplementation.ipynb  # Implementation of RoI transformer
│ ├── UnrotatedBaseline.ipynb  # HBB baseline implementation
│
│── docs/ # Documentation & report drafts
│
│── README.md # Project overview
│── .gitignore
```


## 📊 Datasets
HRSC2016: High-Resolution Ship Collection (ships with oriented bounding boxes).

DOTA: Dataset for Object Detection in Aerial Images (multi-class rotated objects).

NWPU VHR-10: Dataset for Object Detection in Aerial Images (multi-class rotated objects with COCO-style annotations)


## 🚀 Project Goals

Implement and visualize Horizontal → Rotated RoI transformation.

Train/test a baseline detector (horizontal bboxes).

Extend to predict rotated bounding boxes.

Compare baseline vs rotated detectors.
