# Tensorflow Installation Instructions


```{bash}

## Download and install anaconda
wget https://repo.continuum.io/archive/Anaconda3-4.3.1-MacOSX-x86_64.sh
bash Anaconda3-4.3.1-MacOSX-x86_64.sh
conda --version

## Create an environment for tensorflow
conda create -n tensorflow
source activate tensorflow

## Install using conda
conda install tensorflow

## Install tensorflow (without GPU support)
pip3 install tensorflow

```