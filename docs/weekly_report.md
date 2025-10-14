# 🛰️ Object Detection for Aerial Images (RoI Transformer)
**COMP 478 / COMP 6771**

**Team Members:**  
- Ryan de Barros  
- Sassan Ghazi  
- Muhammad Ashar  
- Harshil Prajapati  

**Week 7 – October 13, 2025**  
**Meeting Time:** 4:00 PM  

---

## 🧾 Weekly Progress Report

### ✅ Summary of Progress
| Member | Work Completed |
|---------|----------------|
| **Harshil (Dataset & Evaluation Lead)** | • Completed dataset setup for **HRSC2016** and **DOTA** (train/val/test splits).<br>• Began integrating evaluation metrics (**IoU**, **mAP**) for horizontal and rotated boxes. |
| **Ashar (Baseline Detector Lead)** | • Trained and validated **YOLOv5** baseline model on two dataset splits.<br>• Collected and documented baseline results (accuracy, precision, recall, confusion matrix). |
| **Ryan (RoI Transformation Lead)** | • Set up Google Colab environment with all dependencies (PyTorch, Ultralytics, OpenCV, Pandas, etc.).<br>• Implemented dataset consistency checks and conversion scripts (HRSC XML → YOLO, DOTA TXT → YOLO).<br>• Structured YOLO directories and generated configuration files (`.yaml`).<br>• Launched baseline **YOLOv5** training on HRSC and DOTA.<br>• Clarified dataset preprocessing: normalization of bounding boxes removes the need for manual resizing, as YOLO automatically handles image scaling during training. |
| **Sassan (Feature Extraction & Report Lead)** | • Structured the **project report in LaTeX**, drafting full *Introduction* and *Methodology* sections.<br>• Incorporated clarification on YOLO’s coordinate normalization in the Methodology section.<br>• Prepared a plan for **feature extraction analysis** (HOG and CNN embeddings) to compare **HBB vs. RRoI** detections once rotation outputs are ready. |

---

## 💬 Meeting Notes
- Confirmed **HRSC2016** as the primary dataset for baseline and rotation testing.  
- Discussed finalizing baseline detector training before implementing the **RoI Transformation** module.  
- Clarified that **manual resizing** of images is unnecessary since YOLO normalizes coordinates and automatically resizes input images at runtime.  
- Outlined the next steps for rotation-aware detection, feature analysis, and report progress tracking.  

---

## 🔮 Week 8 Plan

### 🎯 Group Goals
- Finalize **YOLO baseline results** (mAP, IoU, precision–recall).  
- Implement and test **RoI Transformation** using `cv2.minAreaRect` and `cv2.boxPoints`.  
- Begin **feature extraction and visualization** workflow for HBB outputs.  
- Continue report development (Results & Discussion section outline).  

### 👥 Member Tasks
| Member | Next Steps |
|---------|------------|
| **Harshil** | • Complete evaluation metrics for rotated bounding boxes.<br>• Generate plots for precision–recall and mAP comparisons. |
| **Ashar** | • Finalize YOLOv5 training across all dataset splits.<br>• Export trained model weights and inference samples for RRoI testing. |
| **Ryan** | • Implement and test **HBB→RRoI conversion** using OpenCV geometry methods.<br>• Visualize and validate rotated bounding boxes on HRSC images. |
| **Sassan** | • Begin **feature extraction** from baseline YOLO detections (HOG and CNN embeddings).<br>• Create visualizations (PCA/t-SNE) to assess class clustering.<br>• Extend **LaTeX report** with *Results & Discussion* section framework. |

---

## ⚠️ Risks & Notes
- Large dataset size (~8 GB) may increase training time on limited GPU resources.  
- Team should maintain consistent file and label naming to ensure smooth integration between YOLO outputs and RoI transformation scripts.  
- Rotation-based training may require additional validation to avoid coordinate misalignment errors.  

---

## 📦 Deliverables for Week 8 Meeting
1. Final YOLOv5 baseline metrics (accuracy, mAP, precision/recall).  
2. Initial **RoI Transformation** visual samples (rotated bounding boxes).  
3. Early **feature extraction notebook** comparing HBB feature representations.  
4. Updated LaTeX report (Introduction, Methodology, Results structure).  

---
