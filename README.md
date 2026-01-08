# NKUST Neural Network Final Project (AICUP)

This repository contains the code for dataset preparation, model training, and inference.
All experiments are executed in Google Colab.

## Environment
- Platform: Google Colab
- Python: 3.x
- Libraries:
  - ultralytics
  - gdown
  - numpy
  - pillow
  - matplotlib

## Install (Colab)
```bash
pip install ultralytics gdown
```

## Dataset Structure (Input)
```
training_image/
 └─ patient*/
    └─ *.png

training_label/
 └─ patient*/
    └─ *.txt
```

## Label Format
```
class_id x_center y_center width height
```

## Workflow Overview
The complete workflow includes dataset downloading, preprocessing, model training, and inference.
All steps are implemented in the notebook 期末程式.ipynb.

### Dataset Download
Input:
- Google Drive file IDs

Output:
- training_image.zip
- training_label.zip
- aortic_valve_colab.yaml

### Dataset Preparation
Input:
- training_image/
- training_label/

Processing:
- Unzip datasets
- Train/validation split by patient ID
- 1:1 balancing between positive and negative samples
- Negative samples are created with empty label files

Output:
```
datasets/
 ├─ train/images
 ├─ train/labels
 ├─ val/images
 └─ val/labels
```

### Model Training
Input:
- Prepared datasets/
- aortic_valve_colab.yaml
- Pretrained YOLOv8 weights

Output:
- Trained model weights (runs/detect/train/weights/best.pt)

### Inference / Prediction
Input:
- Trained model weights
- Test images

Output:
- Prediction results saved in runs/detect/predict/
- Final submission files (if required)

## How to Run
Open and execute: 期末程式.ipynb

## Output Summary
- Prepared dataset: datasets/
- Training weights: runs/detect/train/weights/
- Inference results: runs/detect/predict/
