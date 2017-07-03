# Traffic Sign Classification

## Eva Liu

Traffic Sign Classification

The goals / steps of this project are the following:


**Build a Traffic Sign Recognition Project**

The goals / steps of this project are the following:
* Load the data set (see below for links to the project data set)
* Explore, summarize and visualize the data set
* Design, train and test a model architecture
* Use the model to make predictions on new images
* Analyze the softmax probabilities of the new images
* Summarize the results with a written report


## Rubric Points
###Here I will consider the [rubric points](https://review.udacity.com/#!/rubrics/481/view) individually and describe how I addressed each point in my implementation.  

---


## 1. Provide a basic summary of the data set. 

I used the pandas library to calculate summary statistics of the traffic
signs data set:

* Number of training examples = 34799;
* Number of validation examples = 4410;
* Number of testing examples = 12630;
* Number of label set examples = 34799;
* Image data shape = (32, 32, 3);
* Number of classes = 43;

## 2. Include an exploratory visualization of the dataset.

Here is an exploratory visualization of the data set. It is a bar chart showing how the data distribute.

![stack Overflow](https://github.com/evaliu1/CarND-Term1-P2/blob/master/distribution.PNG)



# Design and Test a Model Architecture

## 1. Preprocessed the image data. What techniques were chosen and why did you choose these techniques?

As a first step, I decided to convert the images to grayscale because this will change the image from 3 RGB layers to 1 layer.
Here is an example of a traffic sign image before and after grayscaling.

![alt text](https://github.com/evaliu1/CarND-Term1-P2/blob/master/colored_img.PNG)
![alt text](https://github.com/evaliu1/CarND-Term1-P2/blob/master/gray_img.PNG)

As a last step, I normalized the image data so it will give me the mean value 0 for distribution.

I decided to generate additional data because ... 


## 2. Final model architecture looks like including model type, layers, layer sizes, connectivity, etc.) 

My final model consisted of the following layers:

| Layer         		|     Description	        					| 
|:---------------------:|:---------------------------------------------:| 
| Input         		| 32x32x1 RGB image   							| 
| Convolution 3x3     	| 5x5 stride, same padding, outputs 28x28x6 	|
| RELU					|												|
| Max pooling	      	| 2x2 stride,  outputs 14x14x6 				|
| Convolution 3x3	    | 5x5 stride, same padding, outputs 10x10x16			|
| RELU					|												|
| Max pooling	      	| 2x2 stride,  outputs 5x5x16 				|
| Fully connected		| outputs:120       									|
| Fully connected		| outputs:84       									|
| Fully connected		| outputs:10       									|
| Softmax				| etc.        									|
|						|												|
|						|												|
 


## 3. Describe how you trained your model. The discussion can include the type of optimizer, the batch size, number of epochs and any hyperparameters such as learning rate.

To train the model, I used an ....
* AdamOptimizer for managing learning rate
* Batch Size: 128
* Epochs: 30
* Learning rate: 0.001
* Variables initialized with normal distribution (mean=0, std dev=0.1)
* Biases initialized with zeros

## 4. Describe the approach taken for finding a solution and getting the validation set accuracy to be at least 0.93. 
 
My final model results were: 
* Train Set Accuracy = 0.996
* Validation Accuracy = 0.949
* Test Set Accuracy = 0.931

If a well known architecture was chosen:
* What architecture was chosen?
 I used LeNet Architecture for the training section.
* Why did you believe it would be relevant to the traffic sign application?
Since LeNet is an image process architecture, it implements the pipelining of all the image process layers, including: Image convolution, RULE, image Pooling, image Flatten.

* How does the final model's accuracy on the training, validation and test set provide evidence that the model is working well?
I got 0.949 accuracy for the validation set, so the model works pretty well.
 

# Test a Model on New Images

## 1. Choose five German traffic signs found on the web and provide them in the report. For each image, discuss what quality or qualities might be difficult to classify.

Here are five German traffic signs that I found on the web:

![alt text](https://github.com/evaliu1/CarND-Term1-P2/blob/master/test_Image/test.JPG)
I changed the colored image to gray, and also normalized the images to fit the training set.

## 2. Discuss the model's predictions on these new traffic signs and compare the results to predicting on the test set. At a minimum, discuss what the predictions were, the accuracy on these new predictions, and compare the accuracy to the accuracy on the test set 

Here are the results of the prediction:
Test Set Accuracy = 1.000

| Image			        |     Prediction	        					| 
|:---------------------:|:---------------------------------------------:| 
| Turn Right ahead     		| Turn Right ahead 									| 
| No Pass    			| No Pass										|
| Yield					| Yield											|
| 100 km/h	      		| Bumpy Road					 				|
| Slippery Road			| Slippery Road      							|


The model was able to correctly guess 4 of the 5 traffic signs, which gives an accuracy of 80%. This compares favorably to the accuracy on the test set of ...

####3. Describe how certain the model is when predicting on each of the five new images by looking at the softmax probabilities for each prediction. Provide the top 5 softmax probabilities for each image along with the sign type of each probability. (OPTIONAL: as described in the "Stand Out Suggestions" part of the rubric, visualizations can also be provided such as bar charts)

The code for making predictions on my final model is located in the 11th cell of the Ipython notebook.

For the first image, the model is relatively sure that this is a stop sign (probability of 0.6), and the image does contain a stop sign. The top five soft max probabilities were

### The softmax probabilitise for the 1 th sign are

* The first guess is sign number: 33 , with a probability of: 0.999986
* The second guess is sign number: 11 , with a probability of: 7.2003e-06
* The third guess is sign number: 25 , with a probability of: 3.18806e-06
* The fourth guess is sign number: 21 , with a probability of: 2.60653e-06
* The fifth guess is sign number: 12 , with a probability of: 9.4626e-07


### The softmax probabilitise for the 2 th sign are
* The first guess is sign number: 9 , with a probability of: 0.999958
* The second guess is sign number: 41 , with a probability of: 3.95769e-05
* The third guess is sign number: 12 , with a probability of: 1.36729e-06
* The fourth guess is sign number: 10 , with a probability of: 8.49452e-07
* The fifth guess is sign number: 13 , with a probability of: 1.45176e-07
-----------------------------------------------

### The softmax probabilitise for the 3 th sign are
* The first guess is sign number: 15 , with a probability of: 0.998548
* The second guess is sign number: 12 , with a probability of: 0.00127293
* The third guess is sign number: 8 , with a probability of: 0.000139539
* The fourth guess is sign number: 9 , with a probability of: 3.26851e-05
* The fifth guess is sign number: 13 , with a probability of: 5.85101e-06
-----------------------------------------------

### The softmax probabilitise for the 4 th sign are
* The first guess is sign number: 39 , with a probability of: 0.99997
* The second guess is sign number: 31 , with a probability of: 2.87708e-05
* The third guess is sign number: 19 , with a probability of: 8.52219e-07
* The fourth guess is sign number: 21 , with a probability of: 2.85445e-07
* The fifth guess is sign number: 4 , with a probability of: 2.19135e-08
-----------------------------------------------

### The softmax probabilitise for the 5 th sign are
* The first guess is sign number: 1 , with a probability of: 0.999977
* The second guess is sign number: 0 , with a probability of: 2.35195e-05
* The third guess is sign number: 2 , with a probability of: 4.00764e-08
* The fourth guess is sign number: 38 , with a probability of: 1.40795e-12
* The fifth guess is sign number: 14 , with a probability of: 1.31987e-13
-----------------------------------------------

