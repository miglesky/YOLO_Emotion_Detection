# Emotion Detection with YOLOv5

This project is designed to detect and classify emotions in images using the YOLOv5 object detection model. The model is trained to recognize different emotional expressions from facial images. The project was presented and published at the **OpenReadings 2023** conference.

## Overview

The goal of this project is to detect and classify facial emotions in real-time using a custom YOLOv5 model. The dataset used for training was managed and pre-processed via the **Roboflow** platform, which allowed for efficient annotation and dataset version control. The model was trained with high accuracy, making it capable of detecting and classifying emotions such as joy, sadness, surprise, anger, etc., from facial expressions in images.

This project was officially published and presented at the **OpenReadings 2023** conference. The full abstract and details can be found in the conference proceedings on **page 198**: [OpenReadings 2023 Abstract](https://openreadings.eu/wp-content/abstracts/abstract-2023.pdf).

## Requirements

- Python 3.x
- PyTorch (1.13.0+cu116)
- YOLOv5 repository
- Roboflow API
- Dependencies: `pip install -r requirements.txt`

## Setup

1. Clone the YOLOv5 repository:

    ```bash
    !git clone https://github.com/ultralytics/yolov5
    ```

2. Install the required dependencies:

    ```bash
    %cd yolov5
    %pip install -qr requirements.txt
    %pip install -q roboflow
    ```

3. Import necessary libraries and verify the setup:

    ```python
    import torch
    from IPython.display import Image, clear_output

    print(f"Setup complete. Using torch {torch.__version__} ({torch.cuda.get_device_properties(0).name if torch.cuda.is_available() else 'CPU'})")
    ```

## Dataset

1. The dataset for emotion detection was created and labeled using the **Roboflow** platform.
2. To retrieve the dataset, you will need to use the API key and access your project in Roboflow:

    ```python
    from roboflow import Roboflow
    rf = Roboflow(api_key="YOUR_API_KEY")
    project = rf.workspace().project("PROJECT_NAME")
    dataset = project.version("VERSION_NUMBER").download("yolov5")
    ```

3. Replace `"YOUR_API_KEY"`, `"PROJECT_NAME"`, and `"VERSION_NUMBER"` with the actual values from your Roboflow account.

## Training the Model

After setting up the dataset, you can start training the YOLOv5 model with the following command:

```bash
!python train.py --img 416 --batch 5 --epochs 150 --data {dataset.location}/data.yaml --weights yolov5s.pt --cache
