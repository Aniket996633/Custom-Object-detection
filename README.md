# Custom-Object-detection
Object detection for pedestrian, cyclist, motorcyclist, standard vehicles and non-standard vehicles


Transfer learning is used on Yolo V5 model to train for a custom dataset of above mentioned classes.

## Dataset and annotations
The images were collected from internet via multiple sources. To check whether the images were with valid extension, `imghdr` library was used. The code for the same is given in `check_format.py` file 
Annotations were carried out in Yolo format which requires the class and bounding box co-ordinates to be stored in a text file.
The link is shared below through which annotations were performed.

> https://www.makesense.ai/

The annotated image dataset can be found at below location

> /train_data



## Training 
Training was carried on `Colab`

Different experiments based on selection of images for training set, `batch size` and `epochs` were performed and finally the configuration which gave the best results are given below

```
batch_size = 2
epochs = 60
```
The weights can be found at below location

> /weights


## Inference

To carry out the inference, weight file is provided.
Run the below mentioned command after cloning `YOLO V5` from https://github.com/ultralytics/yolov5 and installing the pre-requisites.

> ! python detect.py --weights <path/to/last.pt> --img 640 --conf 0.25 --source <path/to/test/dataset>
