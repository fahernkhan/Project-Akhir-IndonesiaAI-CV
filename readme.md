# Coral Life Forms Detection for Analysis of Climate Change Impact on Coral Biodiversity

![Coral Reef](coral_reef_image.jpg)

## Overview
Coral reefs are vital ecosystems facing unprecedented threats due to climate change. Our project aims to analyze the impact of climate change on coral biodiversity through the development of a Coral Life Forms Detection system using deep learning techniques.

## Objectives
- Develop deep learning models for identifying and analyzing coral life forms.
- Utilize state-of-the-art object detection algorithms to enhance accuracy and efficiency.
- Provide insights into how climate change affects various coral species and reef dynamics.

## Data Collection
Data is collected using a Remotely Operated Underwater Vehicle (ROV) in the North Bali Sea. Images are manually annotated into distinct coral life form classes.

## Data Preparation
Collected data undergoes preprocessing and augmentation to ensure uniformity and enhance model robustness.

### Original Data
- Train Set: 264 images
- Validation Set: 33 images
- Test Set: 33 images

### After Augmentation
- Train Set: 791 images
- Validation Set: 33 images
- Test Set: 33 images

### Preprocessing Steps
1. **Auto-Orient:** Ensuring images are oriented correctly for analysis.
2. **Resize:** Resizing images to a standardized resolution of 640x640 pixels to maintain consistency.

### Augmentation Techniques
- **Flip (Horizontal, Vertical):** Flipping images horizontally and vertically to increase dataset variability and improve model generalization.
- **Grayscale (15%):** Converting a portion of the images to grayscale, which can help the model generalize better to different lighting conditions.
- **Hue (+/- 15°):** Adjusting the hue of images by up to 15 degrees to introduce variability in color tones, enhancing model robustness to different environmental conditions.

By preprocessing the data and applying augmentation techniques, the dataset is expanded and enriched, providing the deep learning model with more diverse examples to learn from. This process helps improve the model's performance and generalization capabilities when deployed in real-world scenarios.

## Model Development
We implement YOLO (You Only Look Once) object detection algorithm variations, including YOLOv3, YOLOv5, and YOLOv8.
The following YOLO versions were utilized:

- YOLOv3
- YOLOv3u
- YOLOv5s
- YOLOv5m
- YOLOv5l
- YOLOv8n
- YOLOv8s
- YOLOv8m
- YOLOv8l
- YOLOv8x

Each variation offers different architectures and features, allowing us to optimize the accuracy and efficiency of our coral life form detection system.


## Training & Optimization
Models are trained with optimized hyperparameters and augmentation techniques for improved performance.

### Hyperparameters
- Epoch: 100
- Batch Size: 16
- Image Size: 416x416
- Learning Rate: lr0 = 0.01, lrf = 0.0001
- Momentum: 0.937
- Weight Decay: 0.0005
- Optimizer: AdamW

### YOLO Augmentation (Default)
- Mosaic: 1.0
- Translate: 0.1
- Scale: 0.5
- Flip (Horizontal, Vertical): 0.5
- HSV (Hue, Saturation, Value): 0.015, 0.7, 0.4

## Evaluation Metrics
Model performance is evaluated using precision, recall, mean Average Precision at 50 (mAP50), and mean Average Precision between 50 and 95 (mAP(50-95)).

## Results
The table below summarizes the evaluation results of different YOLO model variations:

| Model   | Precision | Recall | mAP50 | mAP(50-95) | Inference Time (ms) |
|---------|-----------|--------|-------|------------|----------------------|
| YOLOv3  | 0.784     | 0.664  | 0.715 | 0.55       | ±18                  |
| YOLOv3u | 0.816     | 0.778  | 0.810 | 0.644      | ±21                  |
| YOLOv5s | 0.755     | 0.510  | 0.562 | 0.310      | ±11                  |
| YOLOv5m | 0.707     | 0.500  | 0.562 | 0.308      | ±10                  |
| YOLOv5l | 0.742     | 0.706  | 0.687 | 0.582      | ±10                  |
| YOLOv8n | 0.840     | 0.625  | 0.750 | 0.538      | ±11                  |
| YOLOv8s | 0.859     | 0.779  | 0.829 | 0.637      | ±11                  |
| YOLOv8m | 0.877     | 0.748  | 0.820 | 0.631      | ±15                  |
| YOLOv8l | 0.843     | 0.768  | 0.828 | 0.660      | ±18                  |
| YOLOv8x | 0.801     | 0.695  | 0.782 | 0.535      | ±5                   |


## Future Improvements
- Implement tracking and counting algorithms to quantify coral population sizes.
- Integrate into the Robot Operating System (ROS) for real-time deployment with underwater robots.
- Establish regular real-time deployment for continuous monitoring and conservation efforts.
