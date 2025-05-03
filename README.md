# Real-Time Waste Classification with YOLOv8 and GPIO Control

## Overview

This project uses a YOLOv8 object detection model to classify waste materials into four categories:

- Glass
- Metal
- Paper
- Plastic

It integrates with a Raspberry Pi using `gpiozero` to enable robotic movement based on object detection.

The system uses real-time webcam input and outputs both predictions and servo commands (for future expansion).

---

## Features

- YOLOv8 object detection (NCNN model)
- Real-time camera input via OpenCV
- Precision-Recall, F1, and confidence metrics tracking
- Confusion matrix for classification accuracy
- Ready-to-integrate GPIO servo control logic
- Visualizations of model performance

---

## Sample Predictions

![val_batch1_labels](https://github.com/user-attachments/assets/aeda9213-587d-40f7-bf09-20646be81309)


---

## Training and Validation Metrics

![results](https://github.com/user-attachments/assets/35b17101-bb3e-495a-b7bb-8d196c9a8793)


---

## Confusion Matrix

Shows classification accuracy per class.
![confusion_matrix_normalized](https://github.com/user-attachments/assets/c758ad85-6912-4e43-8e4d-ee81e2a10baa)


---

## F1 Score vs Confidence

Shows how confident the model is across different materials.

![F1_curve](https://github.com/user-attachments/assets/ef843acf-1d41-4ea7-9b13-7f8d9c8774c1)


---

## Precision-Recall Curve

Shows precision and recall trade-off per class.

![PR_curve](https://github.com/user-attachments/assets/d18d384c-b480-4d5a-bad2-380fe6944275)


---

## Precision vs Confidence

Helps calibrate thresholds.

![P_curve](https://github.com/user-attachments/assets/c9d50bbf-55ee-4f10-acb5-3cc50591f298)


---

## Recall vs Confidence

Tracks detection coverage.

![R_curve](https://github.com/user-attachments/assets/b40a9180-3f01-4beb-9665-3e98a8678f99)


---

## Code Structure

### `run.py`

- Loads the model
- Captures video input
- Performs object detection
- Displays annotated frames in real time

### `robot.py`

- Same as `run.py` with extended servo control (commented for future use)
- Contains placeholder methods for robotic actuation:
  - `lookLeft()`
  - `lookRight()`
  - `moveForward()`

---

## Requirements

- Python 3.8+
- `ultralytics`
- `opencv-python`
- `gpiozero` (for Raspberry Pi servo control)

Install with:

```bash
pip install ultralytics opencv-python gpiozero
