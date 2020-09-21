# YOLOv3 + Deep_SORT

* OpenCV
* sklean
* pillow
* numpy 1.15.0
* tensorflow-gpu 1.13.1
* CUDA 10.0


It uses:

* __Detection__: [YOLOv3] to detect objects on each of the video frames.

* __Tracking__: [Deep_SORT] to track those objects over different frames.


  ## Quick Start

__0.Requirements__

    pip install -r requirements.txt
    
__1. Download the code to your computer.__
   
    
__2. Download [yolo.h5]  __ and place it in `deep_sort_yolov3/model_data/`

    you can download my trained [[yolo.h5]](https://drive.google.com/file/d/1dR15luBLCfrw18oA5SNdS34JeqIa3w_U/view?usp=sharing) for detecting person/car/bicycle,etc.*

__3. Convert the Darknet YOLO model to a Keras model:__
```
$ python convert.py model_data/yolov3.cfg model_data/yolov3.weights model_data/yolo.h5
``` 
__4. Run the YOLO_DEEP_SORT:__

```
$ python main.py -c [CLASS NAME] -i [INPUT VIDEO PATH]

$ python main.py -c person -i ./test_video/testvideo.avi
```

__5. Can change [deep_sort_yolov3/yolo.py] `__Line 100__` to your tracking object__

*DeepSORT pre-trained weights using people-ReID datasets only for person*
```
    if predicted_class != args["class"]:
               continue
    
    if predicted_class != 'person' and predicted_class != 'car':
               continue
```








