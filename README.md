# Dali Data Challenge

Simple prediction model using random forest classifier to check if images of individual objects are barnacles or not.

## Description

An in-depth paragraph about your project and overview of use.

### Limitations

* I cropped every single training and testing image by hand because I tried to do cropping with opencv and couldn't figure it out in time so the margins around the objects of each image as well as the image dimensions are not consistent (the main issue I wanted to takle was the process of classification so I figured the method of obtaining the images was secondary)
* In creating the training data, I cross-referenced the image masks to mark objects as being barnacles vs. nonbarnacles. However, when obtaining testing images, I didn't know with complete certainty what was and wasn't a barnacle because but I used my best judgment (that the open circles weren't barnacles and neither were the snails nor the nails in the frame)
* As mentioned, this classification process only solves a small part of the larger problem and required manually cropped training images as input. Ideally, the general procedure outlined here would be used in conjunction with some other process that correctly find the desired region of barnacles within the green frame (which I tried and failed to do) and extracts the individual barnacle shaped objects in that region. This extraction tool could then replace my many clunky cropped images for both training and testing.

## Getting Started

### Dependencies

* opencv2 for python
* sci-kit learn

### Installing

* File names have been kept from downloaded Barnacle folder
* img1.png and img2.png have been cropped to the main region because I wasn't able to automate the cropping process using opencv
* Testing and training image datasets can be found in directories 'testing' and 'training' respectively, each with subdirectories separating images of barnacle objects and nonbarnacle objects

### Executing program

* Load in classification_functions.ipynb to access the functions used for classification
* Run cells in barnacle_classification.ipynb in sequential order

## Authors

Annie Yuan '28

## Version History: 0.1
