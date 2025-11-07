# 🛰️ Object Detection for Aerial Images (RoI Transformer)
**COMP 478 / COMP 6771**

**Team Members:**  
- Ryan de Barros  
- Sassan Ghazi  
- Muhammad Ashar  
- Harshil Prajapati  

**Week 9 – November 6, 2025**  
**Meeting Time:** 4:00 PM  

---

## 🧭 Overview

The team has migrated from YOLOv5 to a **PyTorch Faster R-CNN**–based pipeline, with HRSC2016 and DOTA datasets fully integrated. The current implementation supports horizontal bounding boxes (HBBs) and includes clear placeholders for adding rotation and RoI Transformer logic.

This week’s goal is to **finalize implementation of the RoI Learner and visualization**, integrate the **third dataset**, and prepare for **training, validation, and result analysis** next week.

---

## ✅ Current Status Summary

| Component | Status | Next Step |
|------------|--------|-----------|
| **Datasets** | HRSC2016 and DOTA loaded with working parsers. | Add third dataset + implement `parse_labels()` for it. |
| **Model** | Standard Faster R-CNN pipeline trained and evaluated successfully. | Extend to include RoI Learner + rotation-aware bounding boxes. |
| **Visualization** | Ready for HBB detections. | Extend to show rotated bounding boxes with OpenCV. |
| **Evaluation** | IoU/mAP supported for horizontal boxes. | Update metrics for rotated IoU (`box_iou_rotated`). |
| **Documentation** | Report introduction and methodology completed. | Add implementation details and results sections. |

---

## 👥 Member Assignments

| Member | Responsibilities (Week 9–10) |
|---------|-------------------------------|
| **Harshil Prajapati (Dataset & Eval)** | • Extract and integrate the **third dataset** into shared drive.<br>• Implement new `parse_labels()` method modeled after HRSC/DOTA parsers.<br>• Begin evaluating rotated IoU once rotation outputs are available. |
| **Muhammad Ashar (Model Lead)** | • Implement the **RoI Learner** and modify the Faster R-CNN model:<br>  → Add `(dx, dy, dw, dh, dθ)` prediction layer.<br>  → Integrate `torchvision.ops.roi_align_rotated`.<br>  → Update loss functions for rotation.<br>• Coordinate with Harshil for full training/validation/testing runs on Colab. |
| **Ryan de Barros (Visualization & Integration)** | • Implement **rotated bounding box visualization** using `cv2.minAreaRect` and `cv2.boxPoints`.<br>• Generate **summary statistics** (class counts, IoU, mAP) and plots.<br>• Support Ashar in verifying the RoI Learner output visually. |
| **Sassan Ghazi (Reporting & Feature Analysis)** | • Update **weekly progress report** and finalize the **LaTeX report structure**.<br>• Draft the *Implementation* and *Results* sections.<br>• Integrate sample figures, metrics, and qualitative comparisons between HBB and RRoI results. |

---

## 🧠 Technical TODOs

1. **Extend the model to rotation-aware RoI Transformer**
   - Add a small fully connected “RRoI Learner” layer after RoI pooling:
     ```python
     self.fc_offsets = nn.Linear(roi_feature_dim, 5)  # (dx, dy, dw, dh, dθ)
     ```
   - Use `torchvision.ops.roi_align_rotated()` for rotated feature extraction.
   - Update regression and loss logic to handle the 5D bounding box parameterization.

2. **Add visualization**
   - Use OpenCV to draw rotated bounding boxes:
     ```python
     rect = ((cx, cy), (w, h), theta * 180 / np.pi)
     box = cv2.boxPoints(rect).astype(int)
     cv2.drawContours(image, [box], 0, (0, 255, 0), 2)
     ```
   - Generate comparison plots for HBB vs. RRoI detections.

3. **Add third dataset**
   - Extract dataset to shared drive.
   - Implement a new `parse_labels()` similar to HRSC/DOTA.
   - Confirm bounding box coordinate formats (HBB or rotated).

4. **Prepare evaluation**
   - Implement rotated IoU and NMS via:
     ```python
     from torchvision.ops import box_iou_rotated, nms_rotated
     ```

5. **Finalize training/testing**
   - Run full experiments on all datasets.
   - Save trained models and evaluation logs.
   - Collect metrics for report and visual analysis.

---

## 🕓 Timeline

| Week | Focus | Deliverables |
|------|--------|--------------|
| **Week 9 (Current)** | Implementation of RoI Learner, visualization, and dataset integration. | Updated notebook with RoI Transformer logic and visualization scripts. |
| **Week 10** | Model training + results collection. | Trained rotation-aware model + evaluation plots + summary tables. |
| **Week 11** | Report finalization and presentation prep. | Final report (LaTeX PDF) + presentation slides. |

---

## ⚠️ Risks & Mitigation

| Risk | Impact | Mitigation |
|------|---------|------------|
| Rotation math errors in RoI Learner | Incorrect orientation predictions | Visualize intermediate boxes to validate geometry. |
| Colab resource/time limits | Training may take too long | Train in smaller batches; checkpoint weights frequently. |
| Dataset coordinate mismatch | Invalid labels or boxes | Visual inspection + consistency checks after parsing. |

---

## 📦 Deliverables for Next Meeting

1. Third dataset extracted and parsed.  
2. RoI Learner implemented in the PyTorch model.  
3. Visualization of rotated bounding boxes.  
4. Initial results and metrics for verification.  
5. Updated LaTeX report draft (Implementation + Results).  

---
