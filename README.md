# Deep Dive into Finetuning LLMs Repo for Code Forward 2023 conference

This repo contains a finetuned Mistral 7B model using the [Ludwig](https://ludwig.ai) framework to answer multiple choice questions related to word scrambling (anagrams) - (i.e.  pplae unscrambled is apple).     There are two notebooks:

* [Notebook for FineTuning - WordScramble-MultipleChoice-Model.ipyndb](WordScramble-MultipleChoice-Model.ipynb)
* [Notebook for Inference/evaluating finetuned model](WordScramble-MultipleChoice-Inference.ipyndb)

The notebooks assume that a Conda environment with Ludwig is already setup.   You can refer to the following for setup

* [How to setup Conda environment](#-Miniconda-installation-steps)
* [Setting-up the virtual env for LLM tasks](#Setting-up-the-virtual-env-for-LLMtasks)

These notebooks were creating using version 0.8.6 of Ludwig. Fine-tuning was done on a single A100 with 80GB of Ram in less than one hour.  If using 4-bit quantization the fine-tuning can be done on less powerful GPUs. Using a virtual Python environment such as Conda or venv is highly recommended - especially if running on a cloud training environment!   
 
If you are looking for the original examples that were presented at the presentation on the Code Forward conference they are here:

1) https://github.com/vmware-ai-labs/VMware-generative-ai-reference-architecture/tree/main/Examples/LLM-fine-tuning-example

Note: If one is running on Google Coloab or Paperspace or other cloud environments that allows one to run Jupyter Notebooks with tensorflow/PyTorch, one can skip the part on installing Cuda drivers.

You do need to make the Conda environment available to the Notebook:   

pip install ipykernel (after installing everything else)

python -m ipykernel install --user --name=llm-env

https://github.com/vmware-ai-labs/VMware-generative-ai-reference-architecture/tree/main/Examples/LLM-fine-tuning-example

2)   https://predibase.com/blog/fine-tuning-mistral-7b-on-a-single-gpu-with-ludwig

Tip: You definitely want to use a Virtual Python environment if you just follow the above tutorial.


# Miniconda installation steps

We recommend the use of [Miniconda](https://docs.conda.io/en/latest/miniconda.html) as the Python package management 
system over the default distributions embedded in the OS. Here the shell commands you need to run to set up a Python 
environment.<br>

```shell
## Installing Miniconda

# Downloading the latest Miniconda installer for Linux.

wget -nc https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

# Perform a Miniconda silent installation

bash ./Miniconda3-latest-Linux-x86_64.sh -b -p $HOME/miniconda

# Add Conda activation, assuming you use bash as SHELL

eval "$($HOME/miniconda/bin/conda shell.bash hook)"

# With this activated shell, install conda's shell functions

conda init
```
# Python virtual environment setup.

Then run the following commands to create a conda virtual environment:

```shell
## Setting up the virtual env for LLM tasks

# Create the conda virtual env

conda env create -f llm-env.yaml

# Create the virtual env using a conda dependency specification

# - The package versions in the YAML file have been tested by our experiments

conda activate llm-env

# Make Conda Virtual Environment available to Jupyter notebook

python -m ipykernel install --user --name=llm-env
```
