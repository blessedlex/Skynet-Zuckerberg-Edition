# Computing Environment

To run Deepmask and Sharpmask, you will need an installation of Ubuntu 16.04 LTS.
This cannot be a virtual machine, as the environment will need to use Nvidia's drivers.
Additionally, you will need an Nvidia GPU with a compute compatibility of 3.5 or higher.

# CUDA Toolkit

The CUDA toolkit needs to be installed in order for torch to use your GPU's tensor cores for computation.
The link for installation can be found [here](https://developer.nvidia.com/cuda-92-download-archive).
The machine for this project has a 64-bit AMD processor, so an x86_64 architecture was used.

# cuDNN

To install cuDNN, open your web browser to the [install guide](https://developer.nvidia.com/compute/machine-learning/cudnn/secure/v5.1/prod/doc/cudnn_install-txt) and follow the instructions.
You may need to make an account with NVidia in order to download cudNN.

# Torch

Torch installation requires additional steps than provided from [their website](torch.ch) in order to maintain compatibility.
To begin, run the following command.

```
git clone https://github.com/torch/distro.git ~/torch --recursive
cd ~/torch; bash install-deps
```

Then, open `pkg/torch/lib/TH/THAllocator.c` with an editor of your choice, and remove the following code.

At line 108, remove:
```
if (size == 0) {
  return NULL;
}
```

At line 339, remove:
```
if (data == NULL)
  return;
```

After these changes have been made, run the following command to install torch:

```
TORCH_LUA_VERSION=LUA52 ./install.sh
```

Once the script finishes, you will be prompted to prepend the Torch install location to PATH and LD_LIBRARY_PATH.
Type `yes` and press enter to finish the installation.

# LUA Rocks

There are 3 dependencies not natively installed with torch which are required for Deepmask and Sharpmask.
These are coco, inn, and tds.
To install inn and tds, run the following:

```
luarocks install tds
luarocks install inn
```

To install coco, run the following commands:

```
git clone https://github.com/cocodataset/cocoapi.git ~/cocoapi
cd ~/cocoapi
luarocks make LuaAPI/rocks/coco-scm-1.rockspec
```

# Deepmask & Sharpmask

To begin Deepmask/Sharpmask installation, run the following commands:

```
DEEPMASK=~/deepmask
git clone https://github.com/facebookresearch/deepmask.git $DEEPMASK
mkdir -p $DEEPMASK/pretrained; cd $DEEPMASK/pretrained
wget https://dl.fbaipublicfiles.com/deepmask/models/resnet-50.t7
mkdir -p $DEEPMASK/data; cd $DEEPMASK/data
wget http://msvocds.blob.core.windows.net/annotations-1-0-3/instances_train-val2014.zip
wget http://msvocds.blob.core.windows.net/coco2014/train2014.zip
wget http://msvocds.blob.core.windows.net/coco2014/val2014.zip
unzip *.zip
```
