# 🛰️ Object Detection for Aerial Images (RoI Transformer)
**COMP 478 / COMP 6771**

**Team Members:**  
- Ryan de Barros  
- Sassan Ghazi  
- Muhammad Ashar  
- Harshil Prajapati  

**Week 2 – October 6, 2025**  
**Meeting Time:** 4:00 PM  

---

## 🧾 Weekly Progress Report

### ✅ Summary of Progress
| Member | Work Completed |
|---------|----------------|
| **Harshil (Dataset & Evaluation Lead)** | • Downloaded and preprocessed the HRSC2016 dataset (split into train/val/test).<br>• Started implementing evaluation metrics (IoU, mAP) for horizontal and rotated boxes. |
| **Ashar (Baseline Detector Lead)** | • Trained and validated YOLO baseline model on two dataset splits.<br>• Collected baseline accuracy, precision, recall, and visualization samples. |
| **Ryan (RoI Transformation Lead)** | • Completed environment setup (Python, PyTorch, OpenCV, Ultralytics).<br>• Reviewed RoI Transformer paper and clarified integration with the baseline detector. |
| **Sassan (Feature Extraction & Report Lead)** | • Assisted with setup and dataset access.<br>• Began structuring project report (introduction and methodology sections). |

---

## 💬 Meeting Notes
- Confirmed **HRSC2016** as the main dataset for baseline and RoI transformation tests.  
- Decided to finalize baseline detector using **YOLOv8** before implementing rotation.  
- Discussed pipeline flow: baseline → HBB→RRoI transformation → feature extraction → evaluation.

---

## 🔮 Week 3 Plan

### 🎯 Group Goals
- Complete baseline evaluation (mAP, IoU, confusion matrix).  
- Implement and test **RoI Transformation** functions.  
- Create visual comparisons between **HBB vs. RRoI** detections.  
- Continue drafting report (Methodology & Dataset sections).

### 👥 Member Tasks
| Member | Next Steps |
|---------|------------|
| **Harshil** | • Finalize evaluation metric implementation.<br>• Generate plots for precision–recall and mAP curves. |
| **Ashar** | • Train remaining dataset splits.<br>• Provide final YOLO model weights and inference outputs for testing. |
| **Ryan** | • Implement HBB→RRoI conversion using `cv2.minAreaRect` and `cv2.boxPoints`.<br>• Visualize rotated bounding boxes and export transformed object patches. |
| **Sassan** | • Compare feature embeddings between HBB and RRoI patches (HOG/CNN).<br>• Expand “Methodology” section in report. |

---

## ⚠️ Risks & Notes
- Dataset size (~8 GB) may slow training or evaluation on limited hardware.  
- Ensure consistent naming between YOLO outputs and evaluation scripts to streamline integration.

---

## 📦 Deliverables for Week 3 Meeting
1. Final baseline results (accuracy, mAP, precision/recall).  
2. Working RoI Transformation script with visual samples.  
3. Updated project report (Methodology + Dataset sections).  

---
