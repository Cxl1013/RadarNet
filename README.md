## RadarNet
Deep Learning Convolutional-Deconvolutional Framework to short-term Climate Forecasting


## Introduction
RadarNet implements of a Convolutional-Deconvolutional Neural Network (CDNN) to short-term precipitation forecasting. Also provides an estimation of the advection field by using optical flow. 

RadarNet is intended to rapid implementation and testing of Deep Learning architectures to Climate Research. Please refer to documentation for more information.


## Code style
PEP 8 -- Style Guide for Python Code.


## Screenshot
Example of a real 30-min precipitation sequence:

![alt text](/Images/real_sequence_example.png)


Sequence generated by the model:

![alt text](/Images/predicted_sequence.png)


Estimated optical flow:

![alt text](/Images/optical_flow.png)


## Tech/framework used

<b>Built using:</b>
- [PyTorch](http://pytorch.org)


## Features

1. <strong>Training:</strong> Model training with built-in database.
2. <strong>Visualization:</strong> Real time visualization of training Losses.
3. <strong>Forecasting:</strong> Built in forecasting routine to produce 50 min forecast sequences.


## Usage
<h3>1) Training :</h3>
In order to train a model on your data, run the train.py script, The following command line arguments can be passed :</br>
<strong>-arch:</strong> Neural network architecture to be used. Use 'scd' to train the default Convolution Deconvolution architecture.</br>
<strong>-b:</strong> Batch size.</br>
<strong>-e:</strong> Number of epochs.</br>
<strong>-op:</strong> Optimizer, insert 'Adam' to use the Adam optimizer, 'SGD' to stochastic gradient descent.</br>
<strong>Example of code</strong> : `python train.py -arch scd -b 512 -e 300 -op Adam`</br>
<strong>Output</strong>: </br>
- Model's weights are saved in a file inside the `Models/` folder.
- Visdom visualization server shows the progress of the loss real-time for every epoch

<h3>1) Visualization :</h3>
To generate and visualize predictions with your model, run the `viz.py` script with the following commands:</br>
<strong>-arch:</strong> Neural network architecture to be used. Use 'scd' when using Soft Convolution Deconvolution architecture.</br>
<strong>-s:</strong> Starting sequence index from data provided *default=0*.</br>
<strong>-c:</strong> Number of maps to predict *5-minutes forecasting each*.</br>
<strong>-seq:</strong> Type of sequence. Set to 1 to visualize a continuous map sequence with autoregression, 0 to indivudual forecasting for every input.</br>

<strong>Example</strong> : `python viz.py -arch scd -s 600 -c 7 -seq 1`</br>
<strong>Output</strong> : </br>
- The Visdom server window shows the both target and predicted maps starting from example '-s' untill '-s' + '-c'.

## Status
RadarNet is currently under developement.

## Contribute
RadarNet is totally free and open for everyone to use, please feel free to contribute!
<strong>Clone repository to your laptop:</strong>
`git clone https://github.com/nabimaru/RadarNet`


