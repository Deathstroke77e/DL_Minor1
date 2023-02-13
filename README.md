Model was trained on google colab and due to low GPU limits , only CPU was used.
# Question 1
CIFAR-10 Dataset\
The CIFAR-10 dataset consists of 60000 32x32 colour images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images\
Here, target classes are 10 , but we are choosing only 5 which are {airplane,bird,deer,frog,ship}\
Two different types of Data Augmentation is used to make this model more robust - Around 20% of images are rotated by 10 degree and in another 20% of images gaussian noise is added.\ 
Total Training set= 35000 images\ 
Testing set = 5000 images\
Additionaly 5000 random images from testing set is used as validation set.\

CNN model\
Its using 6 convolution layers , 1 Max pool layer and 1 fully connected hidden layer.\ 
No. of filters used in 1st layer is 12 , thats why 12*3 out features in the output layer.\
No. of filters in subsequent layers is increased by a factor of 2 to capture more complex relations between pixels.\ 
Cross Entropy loss is used as its the best loss function when dealing with categorical data.\
For every epoch , validation and training loss is calculated and if validation loss is getting smaller then only model is saved.\
Finally model is tested on test data with an accuracy of 73.8%\
<img width="319" alt="image" src="https://user-images.githubusercontent.com/124059983/218474381-d5b41407-c46c-4510-bbfb-1a3357524eb2.png">


# Question 2
Using the same CIFAR-10 Dataset ,an autoencoder with 3 layers in encoder and 3 layers in decoder is used.\
Here, mean square error loss is used because here we need to get the loss between reconstructed and input image.\
Using 3 layers of encoding and decoding , the average mean square error was below 0.2.\
Next, the decoder is removed and the encoder parameters are saved and on top of the encoder a fully connected hidden layer of 256 nodes is applied.\
The model is trained using cross entropy as the loss function and testing accuracy was \
<img width="320" alt="image" src="https://user-images.githubusercontent.com/124059983/218472567-ad4ff24d-b333-4bec-8713-7446bbbe57c4.png">


