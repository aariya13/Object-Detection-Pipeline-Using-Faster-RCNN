# Object-Detection-Pipeline-Using-Faster-RCNN

This repository contains a project focused on detecting safety helmets in images using an object detection model built with **PyTorch** Faster RCNN model. The project involves creating a custom dataset, training a model for object detection, and then validating the model using real-world images. The model can identify whether workers are wearing helmets in various scenarios, an important task for workplace safety monitoring.

## Key Components:
1. **Dataset**:
   - The dataset consists of images of workers, either wearing helmets or not, along with corresponding annotations (bounding boxes around helmets).
   - Images are in PNG format, and annotations are stored in XML files.

2. **Model**:
   - The project uses a **pre-trained model** (e.g., Faster R-CNN) fine-tuned for helmet detection. 
   - The model is trained on a custom dataset and detects helmets with high accuracy.

3. **Transformations**:
   - Custom transformations are applied to the dataset, including resizing and normalization of images for optimal training.
   - Bounding box coordinates are also transformed alongside the images for data augmentation.

4. **Training**:
   - The model is trained using the custom dataset with PyTorch's built-in object detection utilities.
   - Training includes the use of data augmentation and appropriate loss functions to improve model performance.

5. **Evaluation and Validation**:
   - The trained model is evaluated on unseen validation data.
   - Predictions are compared against the ground truth (actual bounding boxes and labels) to assess the model’s performance.


## Workflow:
1. **Load the Best Model**: 
   - A pre-trained model is loaded along with its weights to make predictions.
   
2. **Set a Detection Threshold**: 
   - The threshold determines the confidence level at which bounding boxes are displayed. Boxes with a score below the threshold are discarded.

3. **Perform Inference**:
   - The `compare_prediction_with_actual` function is used to run inference on a given image, compare predicted boxes with actual boxes, and visualize the results.

4. **Visualize Results**:
   - The results are visualized by overlaying the predicted and actual bounding boxes on the input images. The predicted bounding boxes are drawn in yellow, red, or blue, while the actual bounding boxes are shown in green.


## Requirements:
  - Python 3.x
  - PyTorch
  - Albumentations
  - Matplotlib
  - NumPy
  - OpenCV

## Reference:
https://www.kaggle.com/datasets/andrewmvd/hard-hat-detection/data
