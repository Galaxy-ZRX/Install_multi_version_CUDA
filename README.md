# Install_multi_version_CUDA

Guidance on how to use module command to load and unload multiple version of CUDA and CUDNN.

Adding the belowing codes in zshrc/bashrc according to your settings.

```
# cuda
module() { eval `/usr/bin/modulecmd zsh $*`; }
module use ~YOUR_DIR/modulefiles

alias cuda9='module unload cuda cudnn && module load cuda/9.0 cudnn/v7.3-cuda-9.0'
alias cuda11='module unload cuda cudnn && module load cuda/11.0 cudnn/v8.0-cuda-11.0'
```

There should be 4 folders in your **modulefiles** folder: cuda, cudnn, cuda_files and cudnn_files. The files in cuda and cudnn should be in the same format of examples.  The root_path need to be modified.

The **cudnn_files** and **cuda_files** should contain the downloaded folder named like '**cuda_9.0**' from official nvidia website.

When change the CUDA version (e.g. change to CUDA11.0 with cudnn v8.0) , using commands:

```
cuda 11
```
