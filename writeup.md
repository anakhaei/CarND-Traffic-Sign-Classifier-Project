## Build a Traffic Sign Recognition Project 

The goals / steps of this project are the following:
* Load the data set
* Explore, summarize and visualize the data set
* Design, train and test a model architecture
* Use the model to make predictions on new images
* Summarize the results with a written report


[//]: # (Image References)

[image1]: /images/image01.png "exploratory visualization"
[image2]: ./examples/grayscale.jpg "Grayscaling"
[image3]: ./examples/random_noise.jpg "Random Noise"
[image4]: /test_images/image01.png "Traffic Sign 1"
[image5]: /test_images/image02.png "Traffic Sign 2"
[image6]: /test_images/image03.png "Traffic Sign 3"
[image7]: /test_images/image04.png "Traffic Sign 4"
[image8]: /test_images/image05.png "Traffic Sign 5"
[image9]: /test_images/image06.png "Traffic Sign 6"


ere is a link to my [project code](https://github.com/udacity/CarND-Traffic-Sign-Classifier-Project/blob/master/Traffic_Sign_Classifier.ipynb)

### Data Set Summary & Exploration

Here is a statistic about the training data set, validation data set and test data set that I used in this project: 

* Number of training examples = 34799
* Number of validation examples = 4410
* Number of testing examples = 12630
* Image data shape = (32, 32, 3)
* Number of classes = 43

The following figure presents the first image of each class from the training data set. Also, the histogram visulize the number of images in each class of the training dataset:

![][image0]


### Design and Test Method Architecture
#### Preprocessing
Regarding the preprocessing, I used 2 methods:

* Shuffling the data set: It is important to shuffle the training data, so that we do not obtain entire minibatches of highly correlated examples.

*  Normalizing the data set: It's simply a case of getting all your data on the same scale. Ensuring standardised feature values implicitly weights all features equally in their representation.

Also rotation and translation are two intersting methods to try. I have not implemented them, but I can see the benefits of these preprocessing methods.

#### Architecture
The network similar to LeNet lab was used in this project. The slight difference in the network is the size of the output. Here is architecture:

* Layer 1: Convolutional. Input = 32x32x3. Output = 28x28x6
* Activation: Relu
* Pooling: Input = 28x28x6. Output = 14x14x6
* Layer 2: Convolutional. Output = 10x10x16
* Activation: Relu
* Pooling. Input = 10x10x16. Output = 5x5x16.
* Flatten. Input = 5x5x16. Output = 400
* Layer 3: Fully Connected. Input = 400. Output = 1024
* Activation: Relu
* Layer 4: Fully Connected. Input = 1024. Output = 1024
* Activation: Relu
* Layer 5: Fully Connected. Input = 1024. Output = 43

#### Training Method
I used 20 ephoches with 128 images in each batch. I noticed the accuracy will change that much after 10 epoches. Probably, other preprocessing method or some changes in the architecture will help. 
Regarding the optimizer, AdamOptimizer was used with teh accuracy rate of 0.001.

Since we had 3 different data set from the begining (Train, Valid, Test), we have used each data set for it's dedicated purpose. Traning data set including 34799 items was used in the training phase. Valid data set included 4410 items and at the end, we used 12630 of the Test set to test the model.  

#### Accuracy
At the current state, here is the accuracy of the network:
* validation set accuracy of ~0.943 
* test set accuracy of 0.94

#### Test a Model on New Images
6 German traffic signs found on the web Were used to test th emodel. 
 * The images have different sizes: I'd liek to see what will be the effect of resizing on the performance of my network.
 * Contrast and brightness: From the human point of view, images are in a good shape with a good contrast.
 * Number of similar signs in traning data set is different:
  - Limit 60: 1250
  - Priority road: 1900
  - Double curve: 250
  - Pedestrian: 240
  - Turn Right: 550
  - keep Right: 1820
 
 The following figures presents the signs which were used to test the model:

![][image4] ![][image5] ![][image6] 
![][image7] ![][image8] ![][image9]

Accuracy on my network on these images is 67%

Here are the results of the prediction:

1- image04.png:
* Pedestrians: 100.00%
* Right-of-way at the next intersection: 0.00%
* Children crossing: 0.00%
* General caution: 0.00%
* Road narrows on the right: 0.00%

2- image05.png:
* Turn right ahead: 99.94%
* Ahead only: 0.06%
* Vehicles over 3.5 metric tons prohibited: 0.00%
* Roundabout mandatory: 0.00%
* Go straight or left: 0.00%

3- image03.png:
* Children crossing: 81.17%
* Beware of ice/snow: 16.75%
* Dangerous curve to the right: 2.07%
* Right-of-way at the next intersection: 0.01%
* Road work: 0.00%

4- image06.png:
* Keep right: 100.00%
* Roundabout mandatory: 0.00%
* Speed limit (50km/h): 0.00%
* Speed limit (20km/h): 0.00%
* Speed limit (30km/h): 0.00%

5- image01.png:
* Speed limit (60km/h): 100.00%
* Speed limit (50km/h): 0.00%
* Speed limit (80km/h): 0.00%
* End of speed limit (80km/h): 0.00%
* Go straight or right: 0.00%

6- image02.png:
* No entry: 99.88%
* General caution: 0.12%
* Traffic signals: 0.01%
* Go straight or left: 0.00%
* Stop: 0.00%




