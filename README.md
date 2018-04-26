[//]: # (Image References)
[image1]: ./images/fcn.png
[image2]: ./images/um_000000.png
[image3]: ./images/um_lane_000000.png
[image4]: ./images/um_000090.png
[image5]: ./images/umm_000035.png


# Semantic Segmentation
### Introduction
This project implements pixels semantic segmentation on images from vehicle front camera using a Fully Convolutional Network (FCN).

### Details
The project builds the following FCN:
![FCN][image1]

On the training stage the network uses RBG image and a pixels classification mask:
![Image][image2]![Mask][image3]

This allows the network to classify road pixels on detection stage:
![Sample 1][image4]![Sample 2][image5]


#### Frameworks and Packages
This project uses the following frameworks/packages:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
#### Dataset
[Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) [file](http://www.cvlibs.net/download.php?file=data_road.zip).  

##### Implementation
The implementation uses pre-trained [VGG16](https://s3-us-west-1.amazonaws.com/udacity-selfdrivingcar/vgg.zip) model with added "decoder" layers.

Hyperparameters are:

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Epochs | 10 |
| keep_prob | 0.7 |
| learning_rate | 0.0001 |
| kernel_initializer | random_normal_initializer(stddev=0.01) |
| kernel_regularizer | l2_regularizer(1e-3) |

##### Run
Run the following command to run the project:
```
python main.py
```
You can soft stop training with processing test images by pressing `Ctrl-C`

