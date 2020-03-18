# Trafic_Sign_Recognition

One of the important problems for self-driving cars is to follow traffic signs. A car moves and collects video from the front camera. In each separate image you could localize the signs and after that understand what sign did we find.

The task is to do the classification part.

In this work I am going to develop a traffic sign recognition system. It will take a sign image with a small context around it and classify which of 43 signs it belongs to. 

I am going to use [The German Traffic Sign Recognition Benchmark: A multi-class classification competition](https://www.researchgate.net/publication/224260296_The_German_Traffic_Sign_Recognition_Benchmark_A_multi-class_classification_competition)

Information, provided by autors:
- Single-image, multi-class classification problem
- 43 classes
- More than 50,000 images in total
- Large, lifelike database
- Training images are grouped by tracks
- Each track contains 30 images of one single physical traffic sign
- Image sizes vary between 15x15 to 250x250 pixels
- Images are not necessarily squared
