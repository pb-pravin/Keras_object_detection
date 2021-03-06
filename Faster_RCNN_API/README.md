# Faster_RCNN_API 
Keras implementation of Faster R-CNN architecture: Towards Real-Time Object Detection with Region Proposal Networks.

## NOTE: 
- Refer the corresponding python files for detailed documentations.  
- Terminal support is withdrawn. Use the scripts as importable functions.

## MAIN ADDITIONAL FEATURES:
- Both python-2 and python-3 are supported
- Support for Validation data
- Tensorboard logging of scalar quantities
- Support for four step alternating training
- Easy implementation of new feature extractors like inception-v2, mobilenet (Refer [nn_arch_vgg16.py](https://github.com/Abhijit-2592/Keras_object_detection/blob/master/Faster_RCNN_API/keras_frcnn/nn_arch_vgg16.py) to know how to implement a new architecture)
- The above functionality can be used to convert any classification model in keras into a object detection model using Faster-RCNN

## USAGE:
- Only tensorflow backend is supported. Since the compile time in thenao version is high I have removed the theano support.
- [train_frcnn](https://github.com/Abhijit-2592/Keras_object_detection/blob/master/Faster_RCNN_API/train_frcnn.py): Use for training the model
- The input data should be a text file in the following format

    filepath,x1,y1,x2,y2,class_name
    The images must be manually split into `train` and `valid` sets and should be put inside **/train/** and **/valid/** folders. 
    
    **NOTE

    For example: The contents of the text file should look like this
    
    `/path/train/img_001.jpg,837,346,981,456,cow`
    
    `/path/valid/img_002.jpg,215,312,279,391,cat`

    - The classes will be inferred from the file.
    - The script infers whether is is training or validation data from `/train/` , `/valid/` present in the path
    - The names of folders must be train and valid so that the text file parser picks up training and validation data properly
    
- [test_frcnn](https://github.com/Abhijit-2592/Keras_object_detection/blob/master/Faster_RCNN_API/test_frcnn.py) Use for testing the model on images
- [measure-map](https://github.com/Abhijit-2592/Keras_object_detection/blob/master/Faster_RCNN_API/measure_map.py) Use to measure the Mean Average Precision Metric

Example output:

![ex1](http://i.imgur.com/7Lmb2RC.png)
![ex2](http://i.imgur.com/h58kCIV.png)
![ex3](http://i.imgur.com/EbvGBaG.png)
![ex4](http://i.imgur.com/i5UAgLb.png)
