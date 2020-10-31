# Neural Network Testing Procedure

### Purpose 
Our goal is to determine the accuracy of DeepMask and MultiPathNet when trained with different sizes of training samples.
This will help us determine how much training data is needed for each algorithm to yield acceptable results.

## DeepMask Procedure
1. Establish a threshold value for image difference - 15%
2. Establish a threshold value for output confidence - 80%
3. Create the set of images for testing
    1. These will be used as inputs for each neural network
    2.These will be manually picked from an open source library
4. Create the training sets for our neural networks
    1. The first set will contain 5,000 training samples from the COCO library
        1. 5,000 is considered the standard sample size for training DeepMask
        2. This will be the control set for our experiment
    2. The second set will be comprised of 4,000 samples from the control set
    3. The third set will be comprised of 3,000 samples from the control set
    4. The fourth set will be comprised of 2,000 samples from the control set
    5. The fifth set will be comprised of 1,000 samples from the control set
5. For each training set, the following will be done
    1. A neural network is created and trained with the set
    2. For each image in the testing set, the following will be done
        1. The image will be given as input into the neural network
        2. The resulting output image and confidence value will be recorded
6. For each output set except besides the control set, the following will be done
    1. For each output image, the following will be done
        1. Compare the image of this set to the output of the control set
            1. Calculate the number of different pixels between each image
            2. Calculate the average difference by dividing the number of different pixels by the number of total pixels
        2. Determine if the resulting output is acceptable by comparing the average difference to the image difference threshold value
        3. Verify the results by viewing the image to ensure it resembles the control group’s output
        4. Determine if the confidence is within the output confidence threshold
        5. If the image has an acceptable confidence and visually verified difference, then the case passes
        6. Otherwise, it fails

## MultiPathNet Procedure
1. Once the results have been compared, then the Multipath Network will be trained
2. For the training of the MultiPath Network, we are going to use the same procedure as used before
    1. We will use a different sample size of COCO libraries.
        1. The first sample size will be 1000 pictures.
        2. The second sample size will be 2000 pictures.
        3. The third sample size will be 3000 pictures.
        4. The fourth sample size will be 4000 pictures.
        5. The fifth sample size will be 5000 pictures; this is the control group of this experiment
3. Once the MultiPath network has been trained, we will compile a test dataset of 25 images
4. The first test will be the control group to create the baseline to compare on to each test dataset
5. Once the test has ended, we will take notes of the results and save the pictures
6. Once the control group is created, we can test the rest of the test dataset
    1. Each dataset will be tested through the MultiPath Network.
        1. The control group of the Deepmask model will be used for this section
    2. After each dataset is tested, we will record the results
7. Compiling the results
    1. For each dataset including the control group, we will go through the pictures to see the results of the identification
        1. If the picture created has been successfully identified, it will be identified as a positive.
            1. If the picture is labeled as successful and with the correct identification, it is a true positive
	    2. If the picture is labeled as successful and with the wrong identification, it will be labeled as a false positive
        2. If the picture has been has been labeled as a failed test, then it will be labeled as a negative.
            1. If the picture is labeled as negative and with the wrong identification, it is a false negative
	    2. If the picture is labeled as negative and with the wrong identification, it will be labeled as a true negative.
        3. With the number of precisions and recalls, we can determine the accuracy of the different MultiPath Networks with the value of F1 score
