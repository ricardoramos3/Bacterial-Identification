
# Convolutional neural network for identification of bacteria from 3D fluorescence images

(Associated with Hay and Parthasarathy, *Performance of convolutional neural networks for identification of bacteria in 3D microscopy datasets* (2018))

# Links to Data

Shared data, including all 21000 manually labeled 3D regions of interest.

# Full Data
- https://www.dropbox.com/s/kefg025910tgz5x/vibrio_data_labels.npz?dl=0 - .npz file for all of the extracted Vibrio volumes (potential bacteria voxels) and corresponding labels. See readme_data.txt below. 
- https://www.dropbox.com/s/hi6d1xejnkxz5m2/pseudomonas_data_labels.npz?dl=0 - .npz file for all of the extracted Pseudomonas volumes (potential bacteria voxels) and corresponding labels. See readme_data.txt below. 
- https://www.dropbox.com/s/tj9ewdh9zp1mtfc/readme_data.txt?dl=0 : Information about the above image and label files.


# Notes on the images and the npz file
Each extracted image is 10x30x30 px (4.5 x 4.5 x 8 um), normalized such that it has a standard deviation of 1 and zero mean. The convnet code reshapes the image to be 8x28x28 which is then fed into the neural network.  

# Code

The ConvNet code uses Tensorflow to create a 3D convolutional neural network for binary classification of objects as bacteria or noise.
It takes as input in 8x28x28 pixel images and outputs a class label of 1 or 0 for bacteria or not bacteria respectively. The input takes the form of an npz file containing the images and labels, then performs a train / test split on those images to generate the 
train and test sets, trains the convolutional neural network and finally tests the network outputting the test accuracy.

### How to use the code
The code requires the python packages tensorflow, sklearn, numpy and matplotlib to be installed. It is also necessary to make sure that the path to the npz file containing the images, the variable called "file_loc" in the code, is correct on your machine. 
After that, the code should be usable as is. See Tensorflow's documentation to save a trained network. 
