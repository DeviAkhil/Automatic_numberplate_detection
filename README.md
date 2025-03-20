Project Overview: Number Plate Detection Using VGG16
This project aims to develop a license plate detection system using the VGG16 deep learning model. The system will first detect the number plate in an image and using bounding box,crop the area
Model Architecture
VGG16 (Pretrained on ImageNet) will be used as a feature extractor.
The fully connected layers of VGG16 will be replaced with a custom head to detect license plates.
Modified Architecture:
Input: Vehicle image
Feature Extraction: VGG16 (without the top layers)
Custom Layers:
Flatten
Fully connected layers with ReLU activation
Output layer (bounding box coordinates for plate detection)
Output: Bounding box (x_min, y_min, x_max, y_max)
5. Implementation Steps
Data Preprocessing

Resize images to 224x224 (VGG16 input size).
Normalize pixel values.
Split dataset into training and validation sets.
Building the Model

Load VGG16 without top layers (include_top=False).
Add custom layers for bounding box prediction.
Use Mean Squared Error (MSE) loss for bounding box regression.
Train the model.
License Plate Extraction

Run the trained model on new images to detect plates.
Crop the detected plate from the image
