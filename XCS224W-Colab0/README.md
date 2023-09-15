# XCS224W Colab 0 Student Code Repository
This repository contains all the code for your assignment!

## Running the Jupyter notebook locally

We have created a `Dockerfile` in the `.devcontainer` subirectory. 
If you are using [Visual Studio Code](https://code.visualstudio.com/) 
you can develop directly in container with it. We have provided a 
 `devcontainer.json` configuration file that when executed, will
 build automatically the `Docker` image and start `VSCode` in the container.
 For finding out the prerequisites and how to deal with the configuration file 
 `devcontainer.json` please check the [Remote development in Containers tutorial](https://code.visualstudio.com/docs/remote/containers-tutorial).

 The `Dockerfile` is able to handle systems with or without `GPU`s. By default the 
 `devcontainer.json` builds the image with `GPU` support. If you don't have a `GPU`
 check the comments inside the `devcontainer.json` to be able to change the arguments
 required to build a Docker image without `GPU` support.

 Additionally, in order for `Docker` to be able to access the `GPU`, please install the 
 [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#setting-up-nvidia-container-toolkit)

 If you are not using `Visual Studio Code` as IDE, you should be familiar with `Docker` 
 to be able to extract the build and run parameters from the `devcontainer.json` configuration file
 and execute them manually on your system! 

<br />

## !!! Instructions for MacOS with Apple Silicon devices **only** !!!

<br />

### On MacOS with Apple Silicon (Mx chips) there is a performance degradation of 50% on Docker containes built with ARM architecture. On Docker containers built with amd64 architecture the degradation magnitude is very huge!

<br />

### The setup below therefore is only dedicated to MacOS with Apple Silicon devices in order to leverage best your Mac. **Please note that PyG is not available for **MPS** device and therefore the Apple GPUs cannot be used as of now with PyG**!!! 

<br />


### Step 1: Make sure you have Miniconda installed. More info about Miniconda installation on MacOS can be found [here](https://docs.conda.io/projects/conda/en/latest/user-guide/install/macos.html]).

<br />

### Step 2: create a default conda environment named **xcs224w** with Python 3.8: 

```
conda create --name xcs224w python=3.8 -y
```

<br />

 
### Step 3: activate the just created xcs224w environment:

```
conda activate xcs224w
```

<br />

### Step 4: install first set of required tools in the **xcs224w** environment
```

pip3 install \
    -f https://download.pytorch.org/whl/torch_stable.html \
        "gradescope-utils>=0.4.0" \
        "jupyter>=1.0.0" \
        "matplotlib>=3.2.2" \
        "matplotlib-inline>=0.1.2" \
        "networkx>=2.6.3" \
        "numpy>=1.21.6" \
        "pandas>=1.3.5" \
        "scipy>=1.7.3" \
        "scikit-learn>=1.0.2" \
        "pillow>=7.1.2" \
        "torch==1.13.1" \
        "python-louvain==0.16"

```

<br />

### Step 5: install the second set of required tools in the **xcs224w** environment

```
      
pip3 install \
    "torch-scatter" \
    "torch-sparse" \
    "torch-geometric" \
    "ogb" \
    "deepsnap"

```
