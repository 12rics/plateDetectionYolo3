# keras-yolo3

## Introduction

A keras implementation of YOLOv3 (Tensorflow backend) for car plate detection (ref: [qqwweee/keras-yolo3](https://github.com/qqwweee/keras-yolo3))

## How to use:

### 1) Get the model

Step 1: Download the project:
```
git clone https://github.com/12rics/plateDetectionYolo3.git
```

Step 2: Download the model [plate.h5](https://drive.google.com/open?id=1a7SdZqNH2Ueh0Ohr-oRwftGPKIC3RNXm) to directory directly.

Step 3: If you want to train with existed trained weights, you can run train by below code.
```
python train.py -a train.txt -c class.txt -o yourOutputname.h5 -s existedWeightyouwantoload.h5
```
train.txt is the text file which have paths of image file and the point of bounding boxes.
class.txt is the file which contains classes you want.
If you want to train with existed weights, you must use same class.txt when you use before for training.

### 2) Test the model on image
Run YOLO detection.
```
python yolo_video.py --model_path plate.h5 --classes_path class.txt --image
```
Then input filepath. Output is saved as pictures/test_result.png

![Plate](pictures/plate1.png)

### 3) Test the model on video

Run YOLO detection.
```
python yolo_video.py --model_path plate.h5 --classes_path class.txt --input input_video.mp4 --output output_video.mp4
```
