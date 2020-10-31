![Data-flow-deep-learning](https://user-images.githubusercontent.com/28307295/97768872-4bbdbb80-1af4-11eb-89d1-7cac92275a2e.png)

## Feature List
Resources
[Reference Link](Deepmask:https://towardsdatascience.com/review-deepmask-instance-segmentation-30327a072339)
[Reference Link](MultiPathNet: https://arxiv.org/abs/1604.02135)

### MultiPathNet
1. Object Proposals: These are the objects that are originated
2. RoI-pooling - This looks at different characteristics of the object to help the determine the identification
3. Fovela Structure: This helps with the idea of Context. These sections of the picture are put into different layers and classify the object. The results are brought together to calculate the score. 

### Deepmask:
1. Image classification: This will identify the type of object to search for in the whole picture.
2. Object Detection: The model will determine where the objects exist within the  picture
3. Semantic Segmentation: This focus on deciding the which pixels are included with the type of object
4. Instance Segmentation: This will determine the pixels that belong to a certain instance of the object.
