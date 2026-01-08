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

Install (Colab):
```bash
pip install ultralytics gdown
Dataset Structure (Input)
The dataset is organized as follows after downloading and unzipping:

training_image/
└─ patient*/
└─ *.png

training_label/
└─ patient*/
└─ *.txt

Each image has a corresponding YOLO-format label file with the same filename.

Label Format
YOLO format (normalized coordinates):

arduino
複製程式碼
class_id x_center y_center width height
Workflow Overview
The complete workflow includes dataset downloading, preprocessing, model training, and inference.
All steps are implemented in the notebook 期末程式.ipynb.

1. Dataset Download
Input:

Google Drive file IDs

Output:

training_image.zip

training_label.zip

aortic_valve_colab.yaml

2. Dataset Preparation
Input:

training_image/

training_label/

Processing:

Unzip datasets

Train/validation split by patient ID

1:1 balancing between positive and negative samples

Negative samples are created with empty label files to represent images without objects

Output:

bash
複製程式碼
datasets/
 ├─ train/images
 ├─ train/labels
 ├─ val/images
 └─ val/labels
3. Model Training
Input:

Prepared datasets/

aortic_valve_colab.yaml

Pretrained YOLOv8 weights

Output:

Trained model weights (e.g. runs/detect/train/weights/best.pt)

4. Inference / Prediction
Input:

Trained model weights

Test images

Output:

Predicted results saved in runs/detect/predict/

Final submission files (if required)

How to Run
Open and execute the notebook step by step:

期末程式.ipynb

The notebook includes all required steps for dataset preparation, model training, and inference,
allowing third-party users to reproduce the results.

Output Summary
Prepared dataset: datasets/

Training weights: runs/detect/train/weights/

Inference results: runs/detect/predict/

yaml
複製程式碼
