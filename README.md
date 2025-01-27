# Dali Data Challenge

Simple prediction model using random forest classifier to check if images of individual objects are barnacles or not.

## Description

I first approached this problem a bit too ambitiously. I intended to create a process that would extract the central region (within the green wireframe) of barnacles from larger images and then make an estimate of the number of barnacles in that region with some sort of classification algorithm. And so I began the process of extracting the main region with opencv. I was able to create and dialate a mask of the green wireframe seen in img1.png and img2.png, however, I ran into a major roadblock when trying to extract the region itself and wasn't able to overcome my error in a timely manner.

From there, I pivoted to trying to tackle the classification aspect of the problem with scikit-learn. Taking screenshots of individual barnacle and nonbarnacle objects from img1.png and img.2png, I trained a random forest classifier to recognize and label similar images (test images were taking from unseen_img1.png). The feature of the images that was used to train the model was the normalized color histogram of each image. I thought usng a histogram here would be appropriate as non-barnacle but barnacle shaped objects typically were hollow and so had a darker interior which distinguished them significantly from barnacle objects. Additionally, I included images of objects in a range of light exposure (some objects were better lit than others) to attempt to account for variations in color. In the end, the classifier yielded a 82.29% accuracy rate when used to classify objects cropped from unseen_img1.png.

### Limitations

* I cropped every single training and testing image by hand because I tried to do cropping with opencv and couldn't figure it out in time so the margins around the objects of each image as well as the image dimensions are not consistent (the main issue I wanted to takle was the process of classification so I figured the method of obtaining the images was secondary)
* In creating the training data, I cross-referenced the image masks to mark objects as being barnacles vs. nonbarnacles. However, when obtaining testing images, I didn't know with complete certainty what was and wasn't a barnacle because but I used my best judgment (that the open circles weren't barnacles and neither were the snails nor the nails in the frame)
* As mentioned, this classification process only solves a small part of the larger problem and requires manually cropped training images as input. Ideally, the general procedure outlined here would be used in conjunction with some other process that correctly find the desired region of barnacles within the green frame (which I tried and failed to do) and extracts the individual barnacle shaped objects in that region. This extraction tool could then replace my many clunky cropped images for both training and testing.

### Future Improvements:

Optimally, obtaining the training and testing images would be done with an automated process as mentioned previously. An additional area of improvement in improving the accuracy of the classification could be using deep learning with CNNs. Using CNNs would require a larger training dataset which could readily be provided with an automated image extracting process that finds all (non)barnacle objects in a region rather than individually screenshotting arbitrary samples of objects as I did here. 

## Getting Started

### Dependencies

* python (jupyter notebook)
* opencv 2
* sci-kit learn

### Installing

* File names have been kept from downloaded Barnacle folder
* img1.png and img2.png have been cropped to the main region because I wasn't able to automate the cropping process using opencv
* Testing and training image datasets can be found in directories 'testing' and 'training' respectively, each with subdirectories separating images of barnacle objects and nonbarnacle objects

### Executing program

* Load in classification_functions.ipynb to access the functions used in barnacle_classification
* Run cells in barnacle_classification.ipynb in sequential order in jupyter notebook to see classification process
* find_frame.ipynb doesn't produce significant results but was the start of a process to extract the main region of interest from img1.png and img2.png in the Barnacles directory

## Authors

Annie Yuan '28

## Version History: 0.1
