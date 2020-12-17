# Neural Network Testing Procedure

### Purpose 
Our goal is to determine the accuracy of DeepMask and MultiPathNet when trained with different sizes of training samples.
This will help us determine how much training data is needed for each algorithm to yield acceptable results.

## DeepMask Procedure
1. Creating and training models.
   - Training models are the models that have been trained by an image library. The image library that is being used is COCO.
   - COCO is a labeled image library. The labels in the image tells the type of object in the picture. This allows to stratify random sampling
     - With stratify random sampling, if we use 5,000 pictures COCO will go through different labels, take a few pictures to test with
   - We will plan to use 5,000 pictures from COCO for training and testing. This number was chosen to make a sample large enough to train the models with reasonable time. With each model. A portion of the 5,000 pictures will be put through the Deepmask training script. 
   - We will have 3 different models.
     - The first model will be trained 5,000 pictures. This is the recommended sample size.
       - Use this command to train the model: th train.lua
     - The second model will use 4,000 pictures. This is 80% of the recommended sample size.
       - Use this command to train the model: th train.lua -batch 25
     - The third model will use 1,000 pictures. This is 20% of the recommended sample size.
       - Use this command to train the model: th train.lua -batch 7
   - For testing the models, Deepmask library provides a testing that will each of the models that were trained. For the amount of pictures used, the testing script uses 5,000 pictures as the default.
     - Use this command to test each model: th train.lua -batch 7
   - Once the evaluation has been completed, the script will give 4 different values. They are Mean, Median, IoU@0.5, and IoU@0.7.
     - Record the results for each model.
     - Compare the results
      
## MultiPathNet Procedure
1. Train and Testing the MultiPathNet Models
   - A Deepmask/Sharpmask model is needed to create and train a MultiPathNet model. The default pretrained model DeepMask/SharpMask will be used to train Multipathnet.
     - [Deepmask/Sharpmask Model](https://dl.fbaipublicfiles.com/deepmask/models/sharpmask/model.t7)
   - We have 3 different models 
     - The first model will have a training size of 256. The total recommended sample size.
       - Use this command to train the model: train_nGPU=1 ./scripts/train_multipathnet_coco.sh
     - The second model will have a training size of 204. This is 79% of the recommended sample size.
       - Use this command to train the model: train_nGPU=1 batchSize=51 ./scripts/train_multipathnet_coco.sh
     - The third model will have a training size 52. This is 20% of the recommended sample size.
       - Use this command to train the model: train_nGPU=1 batchSize=13 ./scripts/train_multipathnet_coco.sh
   - We will be using a testing script provided by the MultiPathNet library. We will use 5,000 pictures for the test size.
     - Use this command to test the model: U=1 test_nsamples=5000 ./scripts/eval_coco.sh
2. Once the MultiPath network has been trained and tested, we will randomly choose 25 images as a sanity check.
   - Identify whether the picture is labeled, if labeled does it match the picture
   - Record the results of the sanity check
3. After the sanity check, we record the data for each model.
   - For each model, there are different thresholds.  For each model, recall the average precision and recall for each thresholds. Below are the thresholds.
     - 0.50
     - 0.75
     - .50:0.95
     
