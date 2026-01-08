# NKUST Neural Network Final Project

This repository contains the source code for the NKUST Neural Network final project.

## Environment
- Platform: Google Colab
- Language: Python 3
- Libraries:
  - numpy
  - matplotlib
  - pillow

## Dataset Structure
training_image/
└─ patient*/
└─ *.png

training_label/
└─ patient*/
└─ *.txt

## Label Format
YOLO format:

class_id x_center y_center width height (normalized)

## Usage
1. Prepare the dataset following the directory structure above.
2. Modify the following paths in `dataset_statistics.py`:
   - `IMAGE_ROOT`
   - `LABEL_ROOT`
   - `PLOT_DIR`
3. Run the script using the command below:

```bash
python dataset_statistics.py
