# Deep Dive into Finetuning LLMs Repo for Code Forward 2023 conference

Example notebooks to go through:

1) https://github.com/vmware-ai-labs/VMware-generative-ai-reference-architecture/tree/main/Examples/LLM-fine-tuning-example

Note: If one is running on Google Coloab or Paperspace or other cloud environments that allows one to run Jupyter Notebooks with tensorflow/PyTorch,
one can skip the part on installing Cuda drivers.

You do need to make the Conda environment available to the Notebook:   

pip install ipykernel (after installing everything else)

python -m ipykernel install --user --name=llm-env

https://github.com/vmware-ai-labs/VMware-generative-ai-reference-architecture/tree/main/Examples/LLM-fine-tuning-example

2)   https://predibase.com/blog/fine-tuning-mistral-7b-on-a-single-gpu-with-ludwig

Tip: You definitely want to use a Virtual Python environment.  To setup everything

pip install ludwig==0.8.6
pip install lora
