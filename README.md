# Predicting brain activity from word embeddings during natural language comprehension

This tutorial introduces a typical **enc**oding framework for mapping **ling**uistic embeddings onto human brain activity during natural language comprehension. The tutorial includes worked examples for both fMRI and ECoG datasets collected while subjects listened to naturalistic spoken narratives. Two types of word embeddings are obtained based on the stimulus transcripts: static word embeddings from word2vec and contextual word embeddings from GPT-2. Encoding models are estimated using banded ridge regression—this allows us to predict brain activity from word embeddings for left-out segments of data.

Run the following code to set up a `conda` environment called `encling` with some useful packages:
```
conda create -n encling
conda activate encling
conda install -c huggingface transformers
conda install -c conda-forge accelerate
conda install -c pytorch pytorch numpy
conda install -c conda-forge jupyterlab ipywidgets
conda install git matplotlib pandas seaborn
pip install himalaya
```
