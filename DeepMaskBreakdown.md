## Partial Deepmask Breakdown

### This is only a partial breakdown. We realized that we could not get the information needed from a statistical analysis.

DataSampler: This is used to create a DataSampler. This is used for training and evaluation.
  - Function: Init
  - Function: creates a BB struct of bojects for score sampling.
  -Function: get size of epoch
  - Function: It gets a sample
  - Function: mask sampling
  - Function: score head sampler
  - Function: crop bbox b from inp tensor
  - Function crop bbox from mask
  - Function: jitter bbox
  - Function: negative sampling
  
DeepMask: This is the DeepMask AI.
  - Function: This is a initialization for DeepMask. It creates common trunk, mask head, and score head.
  - Function: creates common trunk
  - Function:  creates score branch
  - Function: This is a training function. This function is trunk, maskBranch, and scoreBranch.
  - Function: It is an evaluation.
  - Function: to cuda
  - Function: to float
  - Function: this creates an inference
  - Function: clone
  
 InferDeepMask: This creates a module for DeepMask.
  - Function: have a mask output in a style of a matrix
  - Function: The initialization creates a model, number of proposals, mean, input size, time create scale pyramid, and allocate topScores and topMask
  - Function: This is in charge a forwarding pyramid, scales, trunk,  score and mask branch.
  - Function: many get functions
  - Function: display timer
  
InferSharpMask: This is a inference module for SharpMask. This contains the module, mean, input size, timer, scale pyramid, allocate topScores, topMasks, and topPatches.
	(Many get functions)
  - Function: Display timer
  - Function: forward refinement
  
SharpMask.lua: This is the SharpMask AI. This creates many important things. This creates a bottom-up flow, and refinement modules. 
  - Function: Creates horizontal nets
  - Function: Creates refinement modules
  - Function: Creates refinement modules
  - Function: forward
  - Function: backward
  - Function: zeroGradParameters
  - Function: updateParameters
  - Function: evaluate
  - Function: to cuda
  - Function: to float
  - Function: creates a number of proposals for inference
  - Function: inference/ This is used to create inferences
  - Function: This creates a clone
  
TrainerDeepmask.lua: This is in charge of training DeepMask. It has a Trunk model tree. The trunk tree has mask and score branches.  Trunk is a computer science model.

TrainerSharpMask: This is part of training and testing loops for SharpMask. It uses a Torch.CudaTenser to help train it.

computePurposals.lua: The job of file is to take various images and create a inference image.

evalPerImage.lua: This file focuses on scene evaluation of both DeepMask and SharpMask. This load function and save results. It is incharge of creating inference model, keeps a list of eval image, and coverts props into json. There is a run that runs this file.

evalPerPatch.lua- This in charge of evaluating each patch. This loads the models and config, keeps track of the save directory, has dataloader and mask meter, displays output and concatenate it. It does the evaluation, and logs the samples.

modelUtils- This handles the utilities for models.
  - 13 – 20:  It brings in ‘inn’ and checks to see it exist if not it initialized it.
  - Function – converts linear to convTrunk
  - Function – converts linear to convHeads
  
Train.lua: File in charge of training. It contains the options to run DeepMask and SharpMask. It oversees initializing both models, saving them, and incharge of conducting the training based on File Paths.

TrainMeters.Lua: train the measurements of DeepMask and SharpMask
  - Notes: Uses LossMeter
  - Class Loss Meter: used to measure the average loss
	- Function: initializes the lost module
	- Function: Used to reset the lost module
	- Function: Used to add the sum, while keeping track of n
	- Function: Used to take sum divided by n for the value
  - Class Binary Meter: predicts object score and ground truth object notation
	- Function: Initializes
	- Function: Resets
	- Function: Have target and output. It uses a function called squeeze. It checks to see if it matches.  It then determines the accuracy. Finally it resets the files. I

Ioumeter: measure iou between inferred and ground truth mask
  - Function: It initializes
  - Function: resets
  - Function: This is in charge of calculating the iou meter.
  - Function: Determines the value of iou

Sources:
[Deepmask/Sharpmask](https://github.com/facebookresearch/deepmask)
