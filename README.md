# Emotion Detection with YOLOv5

This project is designed to detect and classify emotions in facial images and live video using the YOLOv5 object detection model. The model is trained to recognize various emotional expressions. The project was presented and published at the **OpenReadings 2023** conference.

## Overview

The goal of this project is to detect and classify facial emotions in real-time using a custom YOLOv5 model. The dataset used for training was managed and pre-processed via the **Roboflow** platform, which allowed for efficient annotation and dataset version control. The model was trained with high accuracy, making it capable of detecting and classifying emotions such as joy, sadness, surprise, anger, and more from facial expressions in both images and live video feeds.

This project was officially published and presented at the **OpenReadings 2023** conference. The full abstract and details can be found in the conference proceedings on **page 198**: [OpenReadings 2023 Abstract](https://openreadings.eu/wp-content/abstracts/abstract-2023.pdf).

## Features

- **Real-time Emotion Detection**: Classify facial emotions such as joy, sadness, surprise, and anger in real-time from a webcam or video feed.
- **YOLOv5 Object Detection**: Utilizes the YOLOv5 model for accurate object detection and emotion classification.
- **Custom Dataset**: The model was trained on a custom dataset that includes various emotional expressions.
- **Roboflow Integration**: Dataset was managed and pre-processed using the **Roboflow** platform.

## Requirements

- Python 3.x
- PyTorch (1.13.0+cu116)
- YOLOv5 repository
- Roboflow API

Install dependencies:

```bash
pip install -r requirements.txt
