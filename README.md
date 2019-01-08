# Epco
EEG classification for amputee rehabilitation

This code predicts the imaginary hand motion of an amputee patient (undergoing phantom limb rehabilitation with and augmented reality-based technology). I used EEG-based signal processing on EEG data extracted from an Emotiv Epoc brain-interface (EDF files) in CSV format. The movements to be detected are six: hand extension, hand contraction, finger waving, close fist, open fist, and turn up-side down.
A short real time demo can be watched in my TED Talk: 

https://youtu.be/e-ZBNtzpF1Q?t=419

Here is the pipeline:

1.	Apply a bank of low pass filters and calculate the covariance matrices, then concatenated all together into a single feature set.
2.	Using these features, train three algorithms: Logistic Regression, Convolutional Neural Network and Recurrent Neural Network. 
3.	The above algorithms produce predictions that are then used to train another set of higher-level algorithms: XGBoost, Recurrent Neural Network, Neural Network and Convolutional Neural Network
4.	Diversity is achieved by running above algorithms with many modifications such as different subsets of metafeatures, Parametric ReLU instead of ReLU as activation, multiple layers, among many others. Also, several models are additionally bagged to increase their robustness. 
5.	A weighted mean of the meta-features above is applied to calculate the final prediction. 

This system for rehabilitation was created at BIOS Colombia (www.bios.co) during my term as a Senior Scientific Researcher, as part of the project REGALIAS.

Dependencies:
Python 2.7
Numpy 1.9.2
Scipy 0.16.0
scikit-learn 0.17.dev0
pyriemann 0.2.2 (from sources)
mne 0.10.dev0 (from sources)
XGBoost 0.40 (from sources)
Theano 0.7.0
CUDA 7.0.27
Keras 0.1.2 (from sources)
Lasagne 0.2.dev1 (from sources)
nolearn 0.6adev (from sources)
hyperopt 0.0.2 (from sources)

