# Predicting brain activity from word embeddings during natural language comprehension

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/snastase/encling-tutorial/HEAD)

This tutorial introduces a typical **enc**oding framework for mapping **ling**uistic embeddings onto human brain activity during natural language comprehension. The tutorial includes worked examples for both fMRI and ECoG datasets collected while subjects listened to naturalistic spoken narratives. Two types of word embeddings are obtained based on the stimulus transcripts: static word embeddings from word2vec and contextual word embeddings from GPT-2. Encoding models are estimated using banded ridge regression—this allows us to predict brain activity from word embeddings for left-out segments of data.

This tutorial can be run interactively online using Google Colab: [`Colab Notebook`](https://colab.research.google.com/drive/1L565z54Oth7oNIbzZDt1pLG-l4iOmRaD?usp=sharing)

Use `git clone https://github.com/snastase/encling-tutorial.git` to download this repository.

If you want to run this tutorial locally on a Mac or Linux machine, you can set up a dedicated computing environment using [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html). If you don't already have a conda installation, you can install [miniconda](https://docs.conda.io/en/latest/miniconda.html)—see below. If you already have a working conda installation, you can skip this step.

If you're on a Windows machine, use [PowerShell](https://docs.microsoft.com/en-us/powershell/), [Cygwin](https://www.cygwin.com/), [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), or [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to log onto the PNI server, then proceed to the following Linux instructions.

If you're on a Linux machine (e.g. the PNI server), you can install miniconda using the following:
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```

If you're on a Mac, you can install miniconda using the following instead:
```
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh -o Miniconda3-latest-MacOSX-x86_64.sh
bash Miniconda3-latest-MacOSX-x86_64.sh
```

Next, navigate into the cloned repo and create a conda environment called `encling` from the `environment.yml` file:
```
conda create -f environment.yml
```

Finally, activate the conda environment and start JupyterLab
```
conda activate encling
```

Now, you should be able to launch `jupyter lab` from the command line and open the `encling_tutorial.ipynb` notebook.

---

Optionally, if you want to use updated versions of the software, you can build the conda environment from scratch:
```
conda create --name encling
conda activate encling
```

Run the following code line-by-line to install the necessary packages into the `encling` environment:
```
conda install -c huggingface transformers
conda install -c conda-forge accelerate
conda install -c pytorch pytorch numpy
conda install -c conda-forge jupyterlab ipywidgets
conda install -c conda-forge scikit-learn
conda install -c conda-forge gensim
conda install git matplotlib pandas seaborn
pip install himalaya voxelwise_tutorials
pip install nilearn surfplot neuromaps mne
```
