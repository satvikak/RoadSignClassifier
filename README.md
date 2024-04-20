# Description
This is the Traffic project from CS50's AI courses. It utilizes TensorFlow to build a neural network to classify road signs based on images. The main data set used is the German Traffis Sign Recognition Benchmark.

# Usage
* The latest version of Python you should use is Python 3.11
* Download the [GTSRB dataset](https://cdn.cs50.net/ai/2023/x/projects/5/gtsrb.zip)
* Move that dataset into the directory
* Within the directory, run "pip3 install -r requirements.txt" to install dependencies
* Type "python traffic.py gtsrb" to run

# Experimentation Process

## Initial Setup
To begin, I started by observing the initial setup provided in the lecture notes. More specifically, this included 1 convolutional layer, 1 max pooling layer, 1 flattening layer, 1 dense hidden layer, 1 dropout layer, and 1 output layer. The 10th Epoch had an accuracy of 5.3% while the overall accuracy was 5.5%. Since this could be much improved, I began experiementing.

## Different Numbers of Convolutional and Pooling Layers
Next, I began experimenting with the different number of convolutional and pooling layers. Since there was just 1 to begin with, I decided to see the effectiveness of using 2 and 3. When I utilized 2 layers, I noticed that the accuracy in the 10th Epoch was 85.7% while the evaluation accuracy was 90.7%. On the other hand, when using 3 layers, I noticed that the accuracy in the 10th Epoch was 83.3% while the evaluation accuracy was 86.7%. Though all three versions ran at almost the same rate, it is clear that using 2 layers is best. Therefore, I continued with this configuration for the next experiments.

## Different Sizes of Filters for Convolutional Layers
To continue, I worked with varying sizes of filters for the convolutional layers. In the current state, the program was using two 32 filters. Therefore, I decided to experiment with two 16 filters and two 64 filters. When utilizing two 16 filters, I noticed that the 10th Epoch accuracy was 84.2% while the evaluation accuracy was 91.2%. This configuration also seemed to run slightly quicker than before. Then, I looked at using two 64 filters. The 10th Epoch accuracy was 90.4% while the evaluation accuracy was 96.2%. This configuration ran at the usual rate. Overall, since two 64 filters ran at a decent speed and had better accuracy, I decided to use it for the following experiments as well.

## Different Pool Sizes for Pooling Layers
Furthermore, I tested the effectiveness of using different pool sizes. In the current state, the pool size was using two (2,2) sizes. So, I decided to experiment with two (3,3) sizes and two (4,4) sizes. In the 10th Epoch, the accuracy of the (3,3) sizes was 59.1%, while the evaluation accuracy was 62.3%. When using two (4,4) sizes, the accuracy of the 10th Epoch was 36.4% while the evaluation accuracy was 38.2%. The overall accuracy may have gone down with these configurations since the images were to generalized rather than specified. So, I continued working with the (2,2) pool size.

## Different Sizes of Hidden Layers
Then, I proceeded to test the different sizes of hidden layers. The current program was using a dense layer with value 128. So, I decided to test values 64 and 256. For a value of 64, the 10th Epoch had accuracy 5.6% while the evaluation accuracy was 5.9%. With a value of 256, the 10th Epoch had an accuracy of 94.2% while the evaluation accuracy was 96.4%. This value also appeared to make the program just slightly slower than previously. Despite the 1s slowdown, I decided to continue working with the value of 256.

## Dropout
Finally, I experimented with the dropout value. Considering the current value was 0.5, I decided to use values of 0.4 and 0.3. When using a dropout of 0.4, the 10th Epoch accuracy was 95.7% while the evaluation accuracy was 96.7%. Alongside this, when using a dropout of 0.3, the 10th Epoch accuracy was 96.6% while the evaluation accuracy was 97.1%. So, in my final model the dropout I decided to use was 0.3.

## Overall Results
In the end, my adjusted model produced an evaluation efficiency of around 97%. Though more improvements can be made with more experimentation, these were the best results I found. 
