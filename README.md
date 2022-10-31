# neural-network-on-digit-classification


Creating a white box neural network to identify handwritten digits.


Dataset:

. Dataset contains a number of picture of hadwritten numbers(0 - 9).

. Each picture of a digit is 28 pixels by 28 pixel.

. We deal with 784 pixels per image of a digit.


Overview:

. What we need to do is use this image to predict what digit that image is for this we put the image in form of a matrix where each coloum of row would indicate a pixel. Then we perform mathematical operations on this neural network and pass it through a neural network.

. We would be using quite a basic neural network with 3 layers.

. First layer would be the input layer.
    -> This layer contains 784 nodes to input each pixel into it.

. Second layer would be the hidden layer.
    -> This layer would consist of 10 nodes.

. Third layer would be the output layer.
    -> This layer also would consist of 10 nodes.
    
. We would use ReLU as are activation function, we could have used tanh or sigmoid as well but ReLU felt easier to work with. Activation function are used to explore more combination and matches to get better and more interesting results.

. We would use e^xi/sigma(j = 1 to j = m)(e^xj) as our softmax function. We use a softmax function inorder to scale down the predict numbers in the range of 0 to 1 so that we can see the result as a probability which is more understandable than a bunch of random numbers.


Math:

.FORWARD PROP:

  . So we start off with our image matrix.
  
  . Since the matrix in term of pixels in each coloumns per rows we transpose our matrix which makes manipulating it a bit easier.
  
  . Now we passs the matrix into the input layer and dot product it with the 10 nodes of our hidden layer and add a bias to it.
  
  . Now this result of this is run through our ReLU activation function.
  
  .ReLU helps us make non linear combination thereby increase results produced compared to just linear combinations.
  
  .ReLU reutrn value 0 when Z < 0 else it return value 1.
  
  . Now this result is multiplied by the weight between hidden and output layer and another bias is added to them.
  
  . With this calculation being done with further pass this result into a softmax function which gives us the results in term of probabilities.
  
  . We are able to dot product these result as we have used them in the form of matrices so performing matrix opertions is possible.
  
  
.BACKWARD PROP:

  . Now moving to margining errors we use a one_hot fix for this.
  
  . The hot fix basically rather than using numeric values larger than 1 creates and null matrix but with lets for a number n the the hot fix matrix would have the whole nth rows 1 rest as zero.
  
  . So this matrix is removed from resultant matrix .
  
  . Then we check for how much contributions do the bias and weight have in causing the error.
  
  . We do all of this using basics of calculus.
  
  . For Z when subtract the hot fix matrix from resultant.
  
  . For W(weights) we take the derivative of Z dot it with thte transpose of the resultant and divide it over number of rows.
  
  . For b(bais) we some derivative of Z over number of rows and divide it by total number of rows.
  
  . Then we find derivative of Z[1] by dotting derivative of z and transpose of the weights and multiply by the derivative of the activation function.
  
  . Then we find derivative of W[1] by dotting derivative of Z[1] with the input matrix's transpose over the number of rows.
  
  . Then we find the derivative of b[1] by summing derivative on Z[1] from 1 to number of roows over the number of rows.
  
  . Now towards the end we update our parameters in the form of :
          (current_matrix) - (alpha)*(d(current_matrix))
  
  . alpha is the learning rate here.
  
  . we do these of W[1], b[1], W[2] and b[2] matrices.
  
  
. Now the parameters are updated we run through the whole process again by passing these new parameters into the same process.

. Learning rate is not found through gradient descent but is set by the user.

. Number of times that the image is run through the neural network is also set by the user.

. If you want to check if the model can attain a certain accuracy or not it can be done with a simple loop with the condition of running the loop until the required accuracy is found.

. This particular model as of now gives around 80-85% accuracy.

                                                               ~ Kaushik Naraynan
