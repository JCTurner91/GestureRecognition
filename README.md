# COS-470 Term-Project: Gesture Recognition

By: Tomomi Bahun and Joshua Turner

## Project Description
This project's goal is to develop an application that recognizes human gestures. The authors utilized YOLOv3 which is one of the deep learning models designed for effective object detection. The main focus of this project is 4 gestures: like, dislike, okay, and stop. Potentially, this application can be integrated for various purposes, such as sign language interpretation/translation and as a communication tool with patients who have speaking difficulties. The development tools below were used in this project:
 - Development Environment: Google Colab
 - Implementation Format: Jupyter Notebook
 - Language: Python
 - Libraries: Pytorch 

## Materials and Methods
### Dataset:
The datasets used in this project were constructed by hand. Most images were taken by the authors, with some being pulled from the internet under open use licensing. Each image was also annotated by the authors, defining bounding boxes using the YOLO annotation format. All annotations were done using the open source annotation tool makesense.ai. Several datasets were created during the process of this project and used to test our pipeline under different conditions. Our original dataset can be found [here](https://drive.google.com/drive/folders/1U-1zOr4m_bvNkX8iCZqK22-GWT4dUjIb?usp=sharing), and includes a variety of both subjects and backgrounds, which tests the model under more extreme variations. An alternate dataset derived to focus strictly on the gestures and minimize exterior features (such as change in background) can be found [here](https://drive.google.com/drive/folders/1Gg4T0KKfSLjxAUNzYfTW5HBIWIVVIvOB?usp=sharing).
### Architecture
For the final implementation of this project a [Faster-RCNN](https://arxiv.org/abs/1506.01497) architecture was chosen, with a pre-built [PyTorch implementation](https://pytorch.org/vision/stable/models.html#faster-r-cnn) being utilized in our pipeline. This implementation was chosen for ease of integration into current pipeline as well as it's pre-built options to include pretrained weights, granting the ability to easily implement transfer learning on both the backbone (ResNet classifier) as well as the rest of the model.
### Methods


## Experimental Validation and Results

## Conclusion

## Discussion

## Outlooks
