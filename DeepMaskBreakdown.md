## Partial Deepmask Breakdown

### This is only a partial breakdown. We realized that we could not get the information needed from a statistical analysis.

DataSampler: This is used to create a DataSampler. This is used for radomize sampling for evaluation.

DeepMask: This is the Deepmask AI. This creates the Deepmask Model
    
SharpMask.lua: This is the SharpMask AI. This creates many important things. This creates a bottom-up flow, and refinement modules. 
  
TrainerDeepmask.lua: This is in charge of training DeepMask. It has a Trunk model tree. The trunk tree has mask and score branches.  Trunk is a computer science model.

TrainerSharpMask: This is part of training and testing loops for SharpMask. It uses a Torch.CudaTenser to help train it.

computePurposals.lua: The job of file is to take various images and create a inference image.

evalPerImage.lua: This file focuses on scene evaluation of both DeepMask and SharpMask. This load function and save results. It is incharge of creating inference model, keeps a list of eval image, and coverts props into json. There is a run that runs this file.

evalPerPatch.lua- This in charge of evaluating each patch. This loads the models and config, keeps track of the save directory, has dataloader and mask meter, displays output and concatenate it. It does the evaluation, and logs the samples.
  
Train.lua: File in charge of training. It contains the options to run DeepMask and SharpMask. It oversees initializing both models, saving them, and incharge of conducting the training based on File Paths.

Sources:
[Deepmask/Sharpmask](https://github.com/facebookresearch/deepmask)
