A [[Neural Network]] for [[Computer Vision]] which extract features from the images, invented by Yann LeCun in 1988. Notes are taken from [this video](https://www.simplilearn.com/tutorials/deep-learning-tutorial/convolutional-neural-network#:~:text=Flattening%20is%20used%20to%20convert,layer%20to%20classify%20the%20image.). 
# Processing Images
## Structure
Structurally, CNN's have 3 layers, which process the image in sequence;
1. The input layer, which is a greyscale image of a single channel
	(You might ask "why greyscale?" In greyscale, the value of the pixel is a single dimension, allowing it to be expressed as a number within the array that will be processed. As such, CNN's only "see" (as in, process images) in black-and-white.)
2. The hidden layers, which contains in sequence;
	- The **[[convolution operation|convolution]]** layer, which uses many matrix filters to perform the convolution operation to detect patterns, or "convolved features."
	- The [[ReLU]] layer, which uses the "Rectified Linear Unit" activation function to "get a rectified feature map of the image," or basically cuts out all features detected by the convolution layer whose probability is low. 
	- The Pooling layer, which uses many filters to detect "edges, corners, eyes, feather's beak" of an image of a mockingbird. It "pools" all of the features together into larger features, such as lines connecting into a corner to create a specific object.
3.  The output layer, which contains all the final outcomes that the neural network can resolve to, like dog, bird, cat, trashcan.

## In Action
Prior to any processing by the neural network, the CNN moves to remove all extraneous data from the image that could confuse the neural network. The neural network is simply trying to classify the object, and so only needs the prominent shape and features of an object. As such, the following steps are centered around removing color, background, and unnecessary detail from the image.

![[InputToFeatureMap.png]]

Convolution networks split images into layers by "striding" through the image with a convolution filter. There are many, many, many filters. Each filter seeks out very specific features within the image, processing them via the [[convolution operation]], creating a "feature map," a matrix of the sum of the pixels in the image to the specific filter.

This "feature map" is then put through the [[ReLU]] function, setting any elements of the feature map that are negative to zero, removing them from the map as whitespace. This produces the "rectified feature map."

The rectified feature map is then fed into the pooling layer, where it is processed by the [[pooling operation]], which again filters like the convolution layer, but instead of multiplying and summing, simply takes the maximum of the elements being filtered, and enters them into another matrix, producing the "pooled feature map." This pooled feature map is a matrix of all the greatest values of the rectified feature map, shrinking the dataset to be more manageable and only contain the most prominent features of the image, like edges and corners. 

This pooled feature map is then "flattened" by changing it into a single linear vector. (a single dimensional array.) This flattened map is then attached to all the other filters that have been similarly processed into a massive linear vector.

![[CNNProcessingFlowGraph.png]]

This massive linear vector is then fed into a neural network for detection classification. Neural networks are more or less black boxes, so not much further can be explained.