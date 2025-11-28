COMP478-DL-Project

Term Project – COMP478: Deep Learning for Image Processing

## Object Detection for Aerial Images Using the RoI Transformer: A PyTorch Reproduction and Multi-Dataset Evaluation

Implementation of concepts from the paper:
“Learning RoI Transformer for Oriented Object Detection in Aerial Images”
by Jian Ding, Nan Xue, Yang Long, Gui-Song Xia, Qikai Lu (CVPR 2019).

Paper PDF (CVPR 2019)


## Repository Structure
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


## Datasets
HRSC2016: High-Resolution Ship Collection (ships with oriented bounding boxes).

DOTA: Dataset for Object Detection in Aerial Images (multi-class rotated objects).

NWPU VHR-10: Dataset for Object Detection in Aerial Images (multi-class rotated objects with COCO-style annotations)


## Project Goals

Implement and visualize Horizontal → Rotated RoI transformation.

Train/test a baseline detector (horizontal bboxes).

Extend to predict rotated bounding boxes.

Compare baseline vs rotated detectors.

## File Structure

In order to run and access the necessary files from the datasets:
drive.mount('/content/drive')
SHARED_PATH = Path("drive/MyDrive/Colab Notebooks/Shared")

The link will have a specific order with the following folders inside:
```
MyDrive/
└── Colab Notebooks/
    └── Shared/
        │
        ├── HRSC2016_Final_Splits/
        │   ├── train/
        │   │   ├── images/
        │   │   └── annotations/
        │   ├── val/
        │   │   ├── images/
        │   │   └── annotations/
        │   └── test/
        │       ├── images/
        │       └── annotations/
        │
        ├── DOTA_Final_Splits/
        │   ├── train/
        │   │   ├── images/
        │   │   └── annotations/
        │   ├── val/
        │   │   ├── images/
        │   │   └── annotations/
        │   └── test/
        │       ├── images/
        │       └── annotations/
        │
        ├── NWPU_VHR-10_Final_Splits/
        │   ├── train/
        │   │   ├── images/
        │   │   └── annotations/
        │   ├── val/
        │   │   ├── images/
        │   │   └── annotations/
        │   └── test/
        │       ├── images/
        │       └── annotations/
        │
        ├── Models/
        │   ├── hrsc_faster_rcnn_model.pth
        │   ├── dota_faster_rcnn_model.pth
        │   ├── nwpu_faster_rcnn_model.pth
        │   └── (any saved checkpoints)
        │
        └── Notebook Files/
            └── our_training_notebook.ipynb
```
The Models/ structure will be created once the model is running the epochs.

The model instantiation uses the path:
MODEL_SAVE_PATH = Path("drive/MyDrive/Colab Notebooks/Models")

The file structure matches the references the exact way so that if any folder is named differently, the code breaks.
The dataset rejects annotations or images that are not paired.

Link: https://drive.google.com/drive/folders/1dhRhgjUKX2C4JHF1E-LpaCIr9wRXlNmz?usp=drive_link


