Requirements
=====================
The code is a modification of the original Tensorflow code for BERT (https://github.com/google-research/bert). 
It has been tested with Tensorflow 1.14 over a single Nvidia V100 GPU. The code should be compatible with TPUs, but it has not been tested on such architecture or on multiple GPUs. Moreover, it uses tf_metrics (https://github.com/guillaumegenthial/tf_metrics) to compute some performance measures.

Installation Instructions
=========================
It is suggested to use a python 3.6 environment to run the experiment. If you're using conda, create a new environment with:

conda create --name ganbert python=3.6
Activate the newly created environment with:

conda activate ganbert
And install the required packages by:

pip install -r requirements.txt
This should install both Tensorflow and tf_metrics.

How to run an experiment
========================
The run_experiment.sh script contains the necessary steps to run an experiment with both BERT and GANBERT.

The script can be launched with:
====================================

sh run_experiment.sh

The script will first download the BERT-based model, and then it will run the experiments both with GANBERT and with BERT.

After some time (on an Nvidia Tesla V100 it takes about 5 minutes) there will be two files in the output: qc-fine_statistics_BERT0.02.txt and qc-fine_statistics_GANBERT0.02.txt. These two contain the performance measures of BERT and GANBERT, respectively.