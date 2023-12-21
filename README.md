# Deep Dive into Finetuning LLMs Repo for Code Forward 2023 conference

This repo contains a finetuned Mistral 7B model using the [Ludwig](https://ludwig.ai) framework to answer multiple choice questions related to word scrambling (anagrams) - (i.e.  pplae unscrambled is apple).     There are two notebooks:

* [Notebook for FineTuning - WordScramble-MultipleChoice-Model.ipyndb](WordScramble-MultipleChoice-Model.ipynb)
* [Notebook for Inference/evaluating finetuned model](WordScramble-MultipleChoice-Inference.ipyndb)

These notebooks were creating using version 0.8.6 of Ludwig. Fine-tuning was done on a single A100 with 80GB of Ram in less than one hour.  Using a virtual Python environment such as Conda or venv is highly recommended - especially if running on a cloud training environment!   
 
If you are looking for the original examples that were presented at the presentation on the Code Forward conference they are here:

1) https://github.com/vmware-ai-labs/VMware-generative-ai-reference-architecture/tree/main/Examples/LLM-fine-tuning-example

Note: If one is running on Google Coloab or Paperspace or other cloud environments that allows one to run Jupyter Notebooks with tensorflow/PyTorch, one can skip the part on installing Cuda drivers.

You do need to make the Conda environment available to the Notebook:   

pip install ipykernel (after installing everything else)

python -m ipykernel install --user --name=llm-env

https://github.com/vmware-ai-labs/VMware-generative-ai-reference-architecture/tree/main/Examples/LLM-fine-tuning-example

2)   https://predibase.com/blog/fine-tuning-mistral-7b-on-a-single-gpu-with-ludwig

Tip: You definitely want to use a Virtual Python environment.  To setup everything

pip install ludwig==0.8.6
