# Traffic Sign Classifier
This project uses deep neural networks and convolutional neural networks to classify [German Traffic Signs](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset).

## German Traffic Signs Dataset
<img src="images/0.png" width="64" /> <img src="images/1.png" width="64" /> <img src="images/2.png" width="64" /> <img src="images/3.png" width="64" /> <img src="images/4.png" width="64" /> <img src="images/5.png" width="64" /> <img src="images/6.png" width="64" /> <img src="images/7.png" width="64" /> <img src="images/8.png" width="64" /> <img src="images/9.png" width="64" />

<img src="images/10.png" width="64" /> <img src="images/11.png" width="64" /> <img src="images/12.png" width="64" /> <img src="images/13.png" width="64" /> <img src="images/14.png" width="64" /> <img src="images/15.png" width="64" /> <img src="images/16.png" width="64" /> <img src="images/17.png" width="64" /> <img src="images/18.png" width="64" /> <img src="images/19.png" width="64" />

<img src="images/20.png" width="64" /> <img src="images/21.png" width="64" /> <img src="images/22.png" width="64" /> <img src="images/23.png" width="64" /> <img src="images/24.png" width="64" /> <img src="images/25.png" width="64" /> <img src="images/26.png" width="64" /> <img src="images/27.png" width="64" /> <img src="images/28.png" width="64" /> <img src="images/29.png" width="64" />

<img src="images/30.png" width="64" /> <img src="images/31.png" width="64" /> <img src="images/32.png" width="64" /> <img src="images/33.png" width="64" /> <img src="images/34.png" width="64" /> <img src="images/35.png" width="64" /> <img src="images/36.png" width="64" /> <img src="images/37.png" width="64" /> <img src="images/38.png" width="64" /> <img src="images/39.png" width="64" />

<img src="images/40.png" width="64" /> <img src="images/41.png" width="64" /> <img src="images/42.png" width="64" /> 

This is a multi-class, single-image classification problem. The dataset is available [here](https://d17h27t6h515a5.cloudfront.net/topher/2017/February/5898cd6f_traffic-signs-data/traffic-signs-data.zip)

* The size of training set is 34,799
* The size of validatiaon set is 4,410
* The size of test set is 12,630
* The shape of a traffic sign image is (32, 32, 3)
* The number of unique traffic signs (labels) is 43

## Architecture Overview
The deep neural network architectures receives an image as input, transform it through a series of hidden layers (e.g Conv, max pooling, relu, full connected etc), and output a vector of logits. Then the logits will be used to measured the probability error in traffic sign classification with softmax and cross entropy.

My final model consisted of the following layers:

| Layer         		|     Description	        					|
|:---------------------:|:---------------------------------------------:|
| Input         		| 32x32x3 image   							|
| Convolution 5x5     	| 2x2 stride, valid padding, outputs 28x28x12 	|
| RELU					|												|
| Max pooling	      	| 2x2 stride,  outputs 14x14x12 				|
| Convolution 5x5	    | 2x2 stride, valid padding, outputs 10x10x20    |
| RELU					|												|
| Max pooling	      	| 2x2 stride,  outputs 5x5x20 				|
| RELU					|												|
| Fully connected		| input 500, output 160        									|
| RELU					|												|
| Dropout				| 50%          									|
| Fully connected		| input 160, output 100        									|
| RELU					|												|
| Dropout				| 50%         									|
| Fully connected		| input 100, output 43        									|

With this neural network architecture, along with other optimization, **the accuracy rate on the test dataset is 96.4%**

## Model Training and Optimization

I am able to achieve the accuracy rate of 96.4% on test dataset and 97.9% on the validation dataset. The 
