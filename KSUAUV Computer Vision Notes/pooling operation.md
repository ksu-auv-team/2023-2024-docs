An operation used by many [[Neural Network]]s to shrink down a data set so it can be more easily processed. 

# Algorithm
We have two matrixes, the original dataset to be pooled, `a`, and the pooling filter, `b`. The elements within `b` do not matter, only the size of `b`.
```python
a = [1,4,5,6,2,9,1,3,1]
b = [0,0,0,0] #The elements do not matter, only that we have established that b has a length of 4.
```
The `b` filter takes in elements from `a` to the limit of it's size, and finds the maximum of the elements taken. Then, it finds the max of the array, or the element with the greatest value.
```python
for i in range(len(b)):
	b[i] = a[i]

print(b) #[1,4,5,6]

max(b) #6
```
Then, the pooling filter, `b`, "strides" by advancing one element in the original matrix, `a`, and finding the maximum again.
```python
stridesize = 1
numberOfStrides = (len(a) - len(b))/stridesize
pooledData = []
for z in range(numberOfStrides):
	for i in range(len(b)):
		b[i] = a[i]
	
	pooledData.append(max(b))
```
The result is a smaller dataset that retains all the greatest data points from the original set.

# Image Processing
In image processing, the process of pooling removes more extraneous data, allowing for the most prominent features of the image, like edges and corners, to be focused on.