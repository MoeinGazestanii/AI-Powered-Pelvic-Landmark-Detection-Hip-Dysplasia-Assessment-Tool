


# AI-Powered Pelvic Landmark Detection & Hip Dysplasia Assessment Tool

An interactive, deep learning-based medical imaging application designed in collaboration with orthopaedic surgeons. This tool automates the detection of critical pelvic landmarks on bilateral X-ray images, calculates key diagnostic angles for **Hip Dysplasia**, and allows specialists to manually fine-tune results via an intuitive user interface.

<p align="center">
  <video src="https://github.com/user-attachments/assets/e928664b-3c7d-400e-8539-21f26d95802b" autoplay loop muted playsinline controls width="100%"></video>
</p>

---

## 🚀 Key Features

* **Automated Landmark Detection:** Utilizes a Deep Learning model trained on **3,455 bilateral pelvic X-ray images** to predict the $(X, Y)$ coordinates of 8 essential anatomical landmarks.
* **Interactive Fine-Tuning (Drag & Drop):** Medical specialists can manually adjust the predicted landmarks to ensure 100% diagnostic accuracy before finalizing results.
* **Dynamic Angle Calculation:** Automatically computes clinical metrics for both the right and left sides immediately upon approval.
* **Anatomical Overlay Visualizer:** Plots diagnostic reference lines (baselines, perpendiculars, and parallel tangents) directly onto the image for clinical verification.
* **Smart History Management:** Features a built-in **Undo** functionality to revert accidental manual adjustments easily.
* **Patient Data Integration:** Supports clinical workflow management by linking analysis directly to the patient's name.
* **Comprehensive PDF Report Export:** Generates a structured PDF summary including patient details, exact coordinate mapping, visual plots, and calculated angles.

---


## 📊 Monitored Landmarks & Clinical Metrics

### 1. Detected Landmarks (8 Points)
The underlying model predicts coordinates on a $512 \times 512$ resolution, which are then precisely mapped back onto the original high-resolution squared dimensions of the X-ray image:

| Right Side (Patient's Right / Image Left) | Left Side (Patient's Left / Image Right) |
| :--- | :--- |
| **RFHC:** Right Femoral Head Center | **LFHC:** Left Femoral Head Center |
| **RLE:** Right Lateral Edge | **LLE:** Left Lateral Edge |
| **RME:** Right Medial Edge | **LME:** Left Medial Edge |
| **RTD:** Right Tear Drop | **LTD:** Left Tear Drop |

### 2. Calculated Clinical Angles
* **Lateral Center-Edge Angle (LCEA):** Calculated by drawing a baseline connecting the `RTD` and `LTD` landmarks. A perpendicular line is dropped through the Femoral Head Center (`FHC`), and the angle is measured between this vertical line and a line extending from the `FHC` to the Lateral Edge (`LE`).
* **Acetabular Index Angle (AI):** Measured between a line passing through the Medial Edge (`ME`) parallel to the `RTD-LTD` baseline, and a line connecting the Medial Edge (`ME`) to the Lateral Edge (`LE`).

---

## 💻 User Interface Workflow

1. **Load Image:** Upload a pelvic digital X-ray image and input the patient's name.
2. **Run Model:** Execute the deep learning backend to automatically plot initial landmark estimates.
3. **Refine & Adjust:** Use the interactive canvas to zoom in and drag-and-drop landmarks to correct any minor layout deviations based on expert judgment.
4. **Approve & Lock:** Click the **Approve** button to lock landmark coordinates, trigger the geometric angle calculations, and render the multicolored evaluation lines.
5. **Export Report:** Save comprehensive metrics directly to a secure, unmodifiable PDF document.

---
🔒 **Confidentiality Notice:** <samp>The source code and trained model weights are private and confidential due to proprietary project requirements and NDA restrictions. Only the UI layout and deployment architecture are public.</samp>
