![Data-flow-deep-learning](https://user-images.githubusercontent.com/28307295/97768872-4bbdbb80-1af4-11eb-89d1-7cac92275a2e.png)

## Feature List
### Resources
![DeepMask](https://towardsdatascience.com/review-deepmask-instance-segmentation-30327a072339) <br>
![MultiPathNet](https://arxiv.org/abs/1604.02135)

### MultiPathNet
1. Object Proposals: These are the objects that are originated (Tsang 3).
2. RoI-pooling - This looks at different characteristics of the object to help the determine the identification (Tsang 4).
3. Fovela Structure: This helps with the idea of Context. It breaks the picture into parts. These parts of the picture are put into different layers and computed. The results are brought together to calculate the score (Tsang 4). 

### Deepmask:
1. Image classification: This will identify the type of object to search for in the whole picture (Zagoruyko et al.).  
2. Object Detection: The model will determine where the objects exist within the  picture (Zagoruyko et al.).
3. Semantic Segmentation: This focus on deciding the which pixels are included with the type of object (Zagoruyko et al.).
4. Instance Segmentation: This will determine the pixels that belong to a certain instance of the object (Zagoruyko et al.).

#### Citations
Tsang, Sik-Ho. “Review: DeepMask (Instance Segmentation).” Medium, Towards Data Science, 19 Dec. 2018, towardsdatascience.com/review-deepmask-instance-segmentation-30327a072339. <br> 
Zagoruyko, Sergey, et al. “A MultiPath Network for Object Detection.” ArXiv.org, Cornell University, 8 Aug. 2016, arxiv.org/abs/1604.02135. 
