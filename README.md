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
training_image/
 └─ patient*/
    └─ *.png

training_label/
 └─ patient*/
    └─ *.txt
class_id x_center y_center width height
datasets/
 ├─ train/images, train/labels
 └─ val/images,   val/labels
