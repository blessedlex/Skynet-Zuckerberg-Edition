# Neural Network Testing Procedure

### Purpose 
We plan on determining the accuracy of facial recognition of Deepmask and Multipath. Our plan is to create multiple datasets to give set up different challenges

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
The image will be given as input into the neural network
The resulting output image and confidence value will be recorded
For each output set except besides the control set, the following will be done
For each output image, the following will be done
Compare the image of this set to the output of the control set
Calculate the number of different pixels between each image
Calculate the average difference by dividing the number of different pixels by the number of total pixels
Determine if the resulting output is acceptable by comparing the average difference to the image difference threshold value
Verify the results by viewing the image to ensure it resembles the control group’s output
Determine if the confidence is within the output confidence threshold
If the image has an acceptable confidence and visually verified difference, then the case passes
Otherwise, it fails

MultiPathNet Procedure:
Once the results have been compared, then the Multipath Network will be trained.
MultiPathNet is a neural network is a network in charge of identifying the objects marked by the MultiPath network
To train the MultiPath Network, we will be using the COCO library
To understand the the training a graph is provided: https://github.com/facebookresearch/multipathnet 
       8. For the training of the MultiPath Network, we are going to use the same procedure as used before.
We will use a different sample size of COCO libraries.
The first sample size will be 1000 pictures.
The second sample size will be 2000 pictures.
The third sample size will be 3000 pictures.
The fourth sample size will be 4000 pictures.
The fifth sample size will be 5000 pictures. This is the control group of this experiment.
       9. Once the MultiPath network has been trained, we will compile a test dataset.
This dataset will be the same in the Deepmask procedure.
This will include consistency across both experiments.
      10.  Next is to create the control group.
The first test will be the control group to create the baseline to compare on to each test dataset.
Once the test has ended, we will take notes of the results and save the pictures.
      11. Once the control group is created, we can test the rest of the test dataset.
Each dataset will be tested through the MultiPath Network.
The control group of the Deepmask model will be used for this section.
After each dataset is tested, we will take notes and screen shots of some of the results.
      12. Compiling the results.
For each dataset including the control group, we will go through the pictures to see the results of the identification.
If the picture created has been successfully identified, it will be identified as a positive.
i. If the picture is labeled as successful and with the correct identification, it is a true positive. If the picture is labeled as successful and with the wrong identification, it will be labeled as a false positive
If the picture has been has been labeled as a failed test, then it will be labeled as a negative.
i. If the picture is labeled as negative and with the wrong identification, it is a false negative. If the picture is labeled as negative and with the wrong identification, it will be labeled as a true negative.
With the number of precisions and recalls, we can determine the accuracy of the different MultiPath Networks with the value of F1 score.
     

Conclusion:
	Through this testing we can make a few conclusions. 
For MultiPathNet, we can determine the necessary amount of sample size. With increasing of the sample size, we can see the difference in the accuracy for the MultiPathNet and Deepmask networks. Through this we can determine the trend of accuracy. It can increase exponentially or plateau as the sample time increases in size.
For deepmask, we can determine the accuracy of the mask. We can see whether objects are left of the category . Also, we can see if the mask does not cover the entire object. 
