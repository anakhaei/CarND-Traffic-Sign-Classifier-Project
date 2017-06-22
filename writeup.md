#**Traffic Sign Recognition** 

**Build a Traffic Sign Recognition Project**

The goals / steps of this project are the following:
* Load the data set (see below for links to the project data set)
* Explore, summarize and visualize the data set
* Design, train and test a model architecture
* Use the model to make predictions on new images
* Summarize the results with a written report


[//]: # (Image References)

[image1]: ./examples/visualization.jpg "Visualization"
[image2]: ./examples/grayscale.jpg "Grayscaling"
[image3]: ./examples/random_noise.jpg "Random Noise"
[image4]: /test_images/image01.png "Traffic Sign 1"
[image5]: /test_images/image02.png "Traffic Sign 2"
[image6]: /test_images/image03.png "Traffic Sign 3"
[image7]: /test_images/image04.png "Traffic Sign 4"
[image8]: /test_images/image05.png "Traffic Sign 5"
[image9]: /test_images/image06.png "Traffic Sign 6"


## Rubric Points
The network in the this project is similar to the network in LeNet lab. 

---
###Writeup / README

####1. Provide a Writeup / README that includes all the rubric points and how you addressed each one. You can submit your writeup as markdown or pdf. You can use this template as a guide for writing the report. The submission includes the project code.

You're reading it! and here is a link to my [project code](https://github.com/udacity/CarND-Traffic-Sign-Classifier-Project/blob/master/Traffic_Sign_Classifier.ipynb)

###Data Set Summary & Exploration

I used the numpy library to calculate summary statistics of the traffic
signs data set:

* Number of training examples = 34799
* Number of validation examples = 4410
* Number of testing examples = 12630
* Image data shape = (32, 32, 3)
* Number of classes = 43


###Design and Test a Model Architecture

####1.LeNet architecture was used as the satrt version. Preprocessing includes normalization and shuffling of the data set.


####2. I used 20 ephoches with 128 images in each batch. Accuracy converged to %75 after 10 epoches. 

My final model results were:
* validation set accuracy of 0.753 
* test set accuracy of 0.752


###Test a Model on New Images

####1. Choose 6 German traffic signs found on the web and provide them in the report. 

Here are five German traffic signs that I found on the web:

![][image4] ![][image5] ![][image6] 
![][image7] ![][image8] ![][image9]


####2. Although the accuracy on the original test images was at 0.75, the outcome of the network prediction was not correct. The problem might be in a disrepancy between the format of the training data and New Images. Investigation in process 

Here are the results of the prediction:

1.image04.png:
* Road work: 100.00%
* Ahead only: 0.00%
* Bumpy road: 0.00%
* General caution: 0.00%
* Go straight or right: 0.00%

2.image05.png:
* Keep right: 92.85%
* Roundabout mandatory: 3.33%
* End of all speed and passing limits: 2.42%
* Turn right ahead: 0.88%
* Speed limit (100km/h): 0.18%

3.image03.png:
* Children crossing: 99.67%
* Wild animals crossing: 0.30%
* General caution: 0.02%
* Bicycles crossing: 0.01%
* Priority road: 0.00%

4.image06.png:
* Yield: 76.38%
* Speed limit (50km/h): 22.93%
* Speed limit (80km/h): 0.56%
* Keep right: 0.11%
* Road work: 0.02%

5.image01.png:
* Stop: 93.24%
* Speed limit (30km/h): 5.83%
* Wild animals crossing: 0.91%
* Keep right: 0.02%
* Speed limit (80km/h): 0.00%

6.image02.png:
* Yield: 100.00%
* Turn left ahead: 0.00%
* Keep right: 0.00%
* Stop: 0.00%
* No vehicles: 0.00%




