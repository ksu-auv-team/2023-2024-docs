#definition
A matrix operation used by the [[Convolution Neural Network]], giving it it's name.

# Algorithm
When moving through a matrix being processed (in the case of the CNN, an array of greyscale pixels), we define a convolution filter and it's size. 
This filter will be represented by matrix `b`. Matrix `a` is our original matrix that we are processing for features.

I'll write it in python.
```python
#Our original matrix to be processed
a = [5,3,2,5,9,7]

#A filter of size 3
b = [1,2,3]
```
The elements of `a` and `b` are multiplied together, and then summed.
```python
productOfAandB = []

for i in range(len(b)):
	productOfAandB.append(a[i]*b[i])

print(productOfAandB) #[5,6,6]

sum(productOfAandB) #17
```
Then the convolution filter, `b`, "strides" by advancing one element forward in the array, and then multiplying and summing again. It does this for the entirety of the set.
```python
stridesize = 1
numberOfStrides = (len(a) - len(b))/stridesize
sumArray = []
for z in range(numberOfStrides):
	productOfAandB = []
	for i in range(len(b)):
		productOfAandB.append(a[i+(z*stridesize)]*b[i])
	
	sumArray.append(sum(productOfAandB))

featuremap = sumArray
```

The resulting array of sums is the "feature map" of the image given that specific filter. 

Note the above example is acting on a one dimensional array. The convolution operation is normally performed on 2D arrays of images, meaning the filters usually operate in two dimensions also.
