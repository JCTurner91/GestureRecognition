# COS-470 Term-Project: Gesture Recognition

By: Tomomi Bahun and Joshua Turner

## Project Description

## Materials and Methods
### Dataset:
The dataset used in this project was constructed by hand. Most images were taken by the authors, with some being pulled from the internet under open use licensing. Each image was also annotated by the authors, defining bounding boxes using the YOLO annotation format. All annotations were done using the open source annotation tool makesense.ai. All images used can be found in the data/gestures_dataset/images folder, and their corresponding YOLO annotations are in data/gestures_dataset/labels. The dataset has grown in size over the time it took to complete this project.
### Architecture
The YOLOv3 object detection architecure was chosen for this project, and it was built using PyTorch. YOLO was chosen for it's wide use in the field and increased speed when compared to other object detection algorithms. The architecture still closely follows the [original paper](https://arxiv.org/abs/1804.02767), and the authors drew inspiration and borrowed code from other open source implementations than can be found [here](https://towardsdatascience.com/training-yolo-for-object-detection-in-pytorch-with-your-custom-dataset-the-simple-way-1aa6f56cf7d9) and [here](https://github.com/eriklindernoren/PyTorch-YOLOv3).
### Methods
The authors began by developing the dataset, collecting over 200 images of the four gestures (like, dislike, ok, and stop) in various locations, styles, and formats. The authors then proceeded to annotate the dataset as metioned in the dataset section. Before beginning the construction of a separate model, an [open source implmentation]((https://github.com/eriklindernoren/PyTorch-YOLOv3)) of YOLOv3 was used to train against the dataset before the authors set out to rebuild the architecture in another environment
The authors than worked to implement the YOLOv3 architecture in Jupyter Notebook so that it could be used more easily in Google Colab. The pipeline was constructed to allow for training over a given number of epochs with validation between each, graphing the resulting loss curves. The architecture was experimented with heavily, including the use of transfer learning from pretrained darknet weights [available online](https://pjreddie.com/darknet/yolo/) as well as with weights initalized over a normal distrobution.
After some experimentation, the dataset was expanded to 400+ images in hopes of attaining better results during training.
[To be continued]

## Experimental Validation and Results

## Conclusion

## Discussion

## Outlooks
