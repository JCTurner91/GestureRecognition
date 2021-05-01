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
For the final implementation of this project a [Faster-RCNN](https://arxiv.org/abs/1506.01497) architecture was chosen, with a pre-built [PyTorch implementation](https://pytorch.org/vision/stable/models.html#faster-r-cnn) being utilized in our pipeline. This implementation was chosen for ease of integration into the current pipeline as well as it's pre-built options to include pretrained weights, granting the ability to easily implement transfer learning on both the backbone (ResNet classifier) as well as the rest of the model.
### Methods
The first step in the process was creating the original dataset. Time was taken to collect a variety of photos and learn the annotation process, and a Python script was written to allow for randomly splitting a dataset into train, test, and validation sets of 70, 20, and 10% respectively. The images and annotations were split into two separate folders (<dataset>/images, and <dataset>/labels), and the train/test/validation splits were handled by collecting paths to the images into text files at the root <dataset> folder. Due to this folder structure, as well as the annotation format used, a customer dataset had to be created to allow for the getting of images and annotations, as well as to convert the standard YOLO format of xywh to xyxy for the bounding boxes. With a new dataset a train/test pipeline could be constructed using the architecture mentioned in the piror section. This pipeline was run over a variety of hyperparameters and it's performance was checked with the utilization of both Adam and SGD optimizers. The final pipeline uses the Adam optimizer with a learning rate of 0.0001 and weight decay of 0.0005, runnng around just 2 epochs. Validation was added to the training pipeline and both the training and validation curves are plotted once training is complete to aid in checking for over and underfitting. The testing process gathers the predicted bounding boxes for IoU calcuations and then runs those through Non-Maximum Suppression with a threshold of 0.05. The accuracy of the predictions that remain are calculated and a confusion matrix for the accuracy of individual classes is plotted.

## Experimental Validation and Results

## Conclusion

## Discussion

## Outlooks
