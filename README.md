# YOLOv5 Medium, YOLOv8 Nano Model Trained on 5 Classes

This repository contains a YOLOv5, YOLOv8n model trained on a dataset that includes 5 classes: Person, Bus, Car, Motorbike, and Bicycle. YOLO (You Only Look Once) is a popular object detection model capable of real-time object detection. The "Medium" variant of YOLOv5 refers to the specific architecture and model size used in this implementation.

![Gif](readme_img/ezgif.com-video-to-gif.gif)


Input: image or camera

Ouput: processed image or frame

# Table of Contents
- [YOLOv5 Medium, YOLOv8 Nano Model Trained on 5 Classes](#yolov5-medium-yolov8-nano-model-trained-on-5-classes)
- [Table of Contents](#table-of-contents)
  - [Model Details](#model-details)
  - [Installation and Dependencies](#installation-and-dependencies)
  - [Usage](#usage)
    - [YoloV5](#yolov5)
    - [YoloV8](#yolov8)
  - [Model Performance](#model-performance)
  - [Training](#training)
  - [Acknowledgments](#acknowledgments)
  - [Author](#author)
  - [Contact](#contact)


## Model Details

- **Model Size**: Medium
- **Classes**: 5 (Person, Bus, Car, Motorbike, Bicycle)
- **Framework**: PyTorch
- **Input Image Size**: 448x448
- **Hyperparameters**: lr0=0.01, lrf=0.01, momentum=0.937, weight_decay=0.0005, warmup_epochs=3.0, warmup_momentum=0.8, warmup_bias_lr=0.1, box=0.05, cls=0.5, cls_pw=1.0, obj=1.0, obj_pw=1.0, iou_t=0.2, anchor_t=4.0, fl_gamma=0.0, hsv_h=0.015, hsv_s=0.7, hsv_v=0.4, degrees=0.0, translate=0.1, scale=0.5, shear=0.0, perspective=0.0, flipud=0.0, fliplr=0.5, mosaic=1.0, mixup=0.0, copy_paste=0.0


## Installation and Dependencies
```bash 
pip install requirements.txt
```

## Usage

To use this YOLOv5 model for transportation detection, follow these steps:

1. Clone this repository:

```bash
git clone https://github.com/hotonbao/YOLOV5.git
cd YOLOV5
```


2. Dowload Weight File:
   
   Weight YoloV5: https://drive.google.com/file/d/1zw0rR7iSfobJ9CwPXe2-YqvjrSmjzt_T/view?usp=sharing

   Weight YoloV8: https://drive.google.com/file/d/1OSU5g3yz-IliqMFQhfbmVp0UA6e5nKcT/view?usp=sharing

   **Notice:** *Replace PATH_MODEL in the configs.py(for YoloV5) file with the pre-trained model file.*
  

3. Run the inference script to perform object detection on an image with FastAPI or Streamlit(YoloV5):
   ### YoloV5 ###

   **FastAPI**:
   ```bash
   python api.py
   ```
   Type "/docs" after link  http://127.0.0.1:8000 to test with any image
   ![image](readme_img/FastAPI.png)

   **Streamlit**:
   
   Notice: Run FastAPI before run Streamlit and open new command line and run:
   ```bash
   streamlit run app.py --server.fileWatcherType=none
   ```
   It will open:

   ![image](readme_img/Streamlit.png)

   ### YoloV8 ###
      ```bash
      cd yolo-v8
      python app.py
   ```
   It will open a window:

   ![image](readme_img/window-yolov8.png)

   It have 3 functions:
   - Load Image
   - Start Camera
   - Stop Camera
   
4. -Ouput shape after inference:
   
   ![image](readme_img/out-put-after-infer.png)

   - 1: is number of batch
   
   - 12348: number of bounding boxes in image.
   - 10=(4+1+5): 
       - x_max, y_max, x_min, y_min (4)
       - confidence score is an object (1)
       - confidence correspond to each class(5).


   -Output  postprocess
   Run test.ipynb file to see output.

   Example:
   
   ![image](readme_img/Out_put.png)

   *It is an object that has 6 arguments equivalent to* 

   **[ xmin, ymin, xmax, ymax, confidence of class, classname ']**

   Description:
   ![image](readme_img/out_put_des.png)
   Confidence score: Prediction score of class.

   *Class name: has been encoded :*
   0: "bicycle",
   1: "bus",
   2: "car",
   3: "motorbike",
   4: "person"
## Model Performance

- Loss 
 ![image](/readme_img/results.png)
- F1 Score For Class :
- ![image](/readme_img/F1_curve.png)

## Training

**Dataset:**
   https://www.kaggle.com/datasets/yusufberksardoan/traffic-detection-project/

Load the dataset link in and enter yolov5-training.ipynb run all cells then download the best m.onnx file.

## Acknowledgments

https://github.com/ultralytics/yolov5/tree/master/models

Visit the link if you want to train the model with many different architectural sizes


## Author

Ho Ton Bao 

## Contact

Phone number : +84949800149

Email: htbqn2003@gmail.com


---
