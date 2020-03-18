# Trafic_Sign_Recognition

One of the important problems for self-driving cars is to follow traffic signs. A car moves and collects video from the front camera. In each separate image you could localize the signs and after that understand what sign did we find.

The task is to do the classification part.

In this work I am going to develop a traffic sign recognition system. It will take a sign image with a small context around it and classify which of 43 signs it belongs to. 

I am going to use [The German Traffic Sign Recognition Benchmark: A multi-class classification competition](https://www.researchgate.net/publication/224260296_The_German_Traffic_Sign_Recognition_Benchmark_A_multi-class_classification_competition)

Information, provided by autors:
- Single-image, multi-class classification problem;
- 43 classes;
- More than 50,000 images in total;
- Large, lifelike database;
- Training images are grouped by tracks;
- Each track contains 30 images of one single physical traffic sign;
- Image sizes vary between 15x15 to 250x250 pixels;
- Images are not necessarily squared;

## Steps

### Download training and testing dataset dataset

Use GTSRB_Final_Training_Images.zip for training and GTSRB_Final_Test_Images.zip + GTSRB_Final_Test_GT.zip for testing

### Transform images to same size

Now train and test images differ in size and shape: some of them are square, others are rectangular.

To be able to produce the same number and kind of features from all images, we must ensure they have the same size. What we can do:

- Padd rectangular images to square shape - add zero pixels to the shorter side;

- When all images have the desired square shape, resize them to the same dimensionality - 30x30 pixels.

 ### Split data
 
We need to write cod for the train-validation split (not using sklearn or any other ready implementation) and split the data in 80%-20% proportion. Pay attention to the fact that images are organized in tracks - there are 30 photos (video frames) for each sign taken from different distances. Make sure that images from the particular track end up being in either training or validation split, otherwise validation will be faulty.

Also we need to shuffle the data.

### Frequencies

We need to find class frequencies in the resulting training set

### Augmentation

We can see from the bar-chat we’ve just produced that the classes are are highly imbalanced.

One of the ways to overcome this problem is to produce synthetic images from the existing ones and then add them to the training set (we already know their labels). This is called data augmentation and it is a very common technique, especially in the images domain. Check these resources (1, 2) to see what are the possible ways to augment your data and choose two-three techniques that are appropriate in our particular case. In the Report you should justify your choice and provide examples of augmentation (original vs augmented images).

The number of images of each class become the same after the augmenation.

### Image normalization

Normalize every image separately such that pixel values are between 0 and 1 for both train and valiation splits.

### What are the features?

Finally, we represented all pixels as a number from 0 to 1. Now for each image we can ravel this matrix and present each sample as 1-dimentional vercor whith the same size.
Stack those vectors to matrix.

### Train model

Train RandomForest trafic signs classifier based on your training data.

