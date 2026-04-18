# Smoke & Fire Detection using YOLOv8
## Automated Object Detection Pipeline with Dynamic YAML Patching
### By Muhammad Auffa Hakim Aditya

This repository contains a clean, streamlined Machine Learning pipeline for training a YOLOv8 Object Detection model to identify smoke and fire in real-time. Built specifically for environments like Google Colab, this project solves one of the most common issues in custom YOLO training: broken dataset configuration paths.

The project was developed by Muhammad Auffa Hakim Aditya to demonstrate practical Computer Vision engineering, focusing on automated data wrangling (YAML patching), efficient model training using the YOLOv8 Nano architecture, and dynamic image inference.

------------------------------------------------------------

PROJECT OBJECTIVES

1. Automated Dataset Provisioning: Download the D-Fire (Smoke & Fire) dataset directly via KaggleHub without manual zip extraction.
2. Dynamic YAML Patching: Automatically intercept and rewrite the `data.yaml` configuration file. This fixes hardcoded local PC paths left by the original dataset creator, ensuring the script runs flawlessly on any cloud or local machine.
3. YOLOv8 Nano Fine-Tuning: Train the lightweight and lightning-fast `yolov8n.pt` model to draw bounding boxes around fire and smoke hazards.
4. Custom Inference Engine: Provide an interactive block for users to upload custom images, run predictions with a specific confidence threshold (`conf=0.25`), and visualize the bounding boxes using OpenCV and Matplotlib.

------------------------------------------------------------

DATASET INFORMATION

Source          : Kaggle (sayedgamal99/smoke-fire-detection-yolo)
Domain          : Disaster Prevention / Computer Vision
Target Classes  : 
- 0: Smoke
- 1: Fire
Input Shape     : 640x640 (Standard YOLO resolution)

------------------------------------------------------------

MACHINE LEARNING PIPELINE ARCHITECTURE

1. Data Wrangling (YAML Fix):
   The script dynamically creates `data_fixed.yaml` in the `/content/` directory, pointing the `train`, `val`, and `test` variables strictly to the correct relative paths within the downloaded KaggleHub cache.

2. Model Architecture (YOLOv8 Nano):
   - Chose the Nano variant (`yolov8n.pt`) for its extremely high FPS (Frames Per Second), making it ideal for real-time CCTV or drone-based disaster monitoring.
   - Trained for 15 epochs with a batch size of 16.

3. Visualization:
   Converts YOLO's native BGR plotted arrays into RGB format so they display correctly inside Jupyter/Colab notebooks using `matplotlib`.

------------------------------------------------------------

INSTALLATION & REQUIREMENTS

Dependencies:
pip install ultralytics kagglehub pyyaml opencv-python-headless matplotlib

------------------------------------------------------------

HOW TO RUN

1. Open the script in Google Colab.
2. Run the cells sequentially. The script will automatically download the dataset, fix the configuration file, and begin training.
3. Once training is complete, run the final inference cell. You will be prompted to upload an image from your computer to test the fire and smoke detection capabilities live.

------------------------------------------------------------

AUTHOR

Muhammad Auffa Hakim Aditya

This project was developed as an exploration of:
- Computer Vision for Disaster Management
- YOLOv8 Object Detection
- Automated Data Engineering (YAML Patching)
- Real-time bounding box inference
