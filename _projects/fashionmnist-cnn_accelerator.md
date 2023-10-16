---
title: "FashionMNIST CNN Accelerator"
permalink: /portfolio/fasionmnist-cnn-hls
excerpt: "CNN accelerator in HLS"
redirect_from:
  - /theme-setup/
toc: true
order: 4
---

Github Repo Link: [https://github.com/beebdev/FashionMNIST-CNN-Accelerator](https://github.com/beebdev/FashionMNIST-CNN-Accelerator)
{: .notice--info}

This is an FPGA accelerator for CNN on the Fashion-MNIST dataset using HLS. The aim of this project is to accelerate the classification task for image recognition on the FashionMNIST dataset. Due to the time limitation of the project duration, our model will only include:
- CONV
- RELU
- POOL
- FC

> This is a course project for COMP4601 @UNSW.

# Repo structure
- cnn_accelerator/ - Includes the C++ source code for FashionMNIST-CNN and Vivado HLS tcl script and directives.
- cnn_training/ - Includes the CNN training code that generates the parameters used in the layers in FashionMNIST-CNN
- data/ - Includes the training and test data sets for MNIST and FashionMNIST

# Quickstart
**Weight training and extraction**
Since we only want to accelerate the classification process, we have a seperate program for training the model and saving the trained parameters to a weights.txt file. The getParameters.py script will scrap the trained weights and produce a weights.h header file saved in the cnn_accelerator/include. This will be compiled to the classification program.

```sh
cd path/to/FashionMNIST-CNN-Accelerator/
cd cnn_training
./train_parameters.sh
```

# Intro
# Introduction

A Convolutional neural network (CNN) is a neural network with one or more convolutional layers and is used mainly for image processing, classification, segmentation, and other autocorrelated data. Since CNN relies heavily on matrix multiplication such as convolution, therefore there exist opportunities for further improving the performance of CNN. The purpose of this project is to explore and exploit the parallelism of CNN algorithms and the performance boost of HLS based accelerators.

The Fasion-MNist (Link) dataset is used as our data sample to perform classification. The training dataset include 60,000 examples while the test set has 10,000 examples. Our C/C++ implementation will train the model based on the training dataset and run classification (prediction) on the test set. The model will use four main types of layers: Convolutional, Relu (Activation), Pooling, and Fully Connected.

We will be using the SimpleCNN C++ library that provides some basic implementations of layers and training flow.

![Alt text](/assets/images/fasionmnist-cnn-accel/fasionmnist.png)

# Project Objectives
In this project, we aim to speed up the training and classification latency for the our CNN model for MNist.

By the end of this project, we hope to obtain:
- Robust understanding of CNN and the underlying computation structures
- Knowledge in bottlenecks for CNN computations
- Skills in analysis software algorithms and applying optimisation
- Experience in developing acceleration design for specific application using HLS
- Experience in developing systems on MPSoC FPGA platforms

# Algorithms to be investigated
## Description
Great effort will be spent on optimising the layers used in the model, specifcally convolutional, relu, pooling, and fully connected. As mentioned in [link] CONV and FC are similar and the only difference is that hte neurons in CONV are connected only to a local region in the input.

## Pseudo-code
**Convolutional Layer**
```c
function conv_layer(input_image):
		Apply padding to input_image
		for i from 0 to x_max:
				for j from 0 to y_max:
						for each filter f:
								out = convolution(window, f) + bias
						end for
				end for
		end for
function end

/* CONV */
float kernel_conv(float din[CONV_IN_DIM_X][CONV_IN_DIM_Y], int x, int y, int filter) {
    /* Map x, y */
    int o_x = x * CONV_STRIDE;
    int o_y = y * CONV_STRIDE;

    float sum = 0;
    for (int i = 0; i < CONV_EXTFILTER; i++) {
        for (int j = 0; j < CONV_EXTFILTER; j++) {
            float f = conv_filter[filter][i][j];
            float v = din[o_x + i][o_y + j];
            sum += f * v;
        }
    }
    return sum;
}

/* Conv_layer
 * din: 2D array of 28*28
 * dout: 3D array of */
void conv_layer(float din[CONV_IN_DIM_X][CONV_IN_DIM_Y], float dout[CONV_OUT_DIM_X][CONV_OUT_DIM_Y][CONV_OUT_DIM_Z]) {
    for (int filter = 0; filter < CONV_NFILTERS; filter++) {
        for (int x = 0; x < CONV_OUT_DIM_X; x++) {
            for (int y = 0; y < CONV_OUT_DIM_Y; y++) {
                // Call kernel convolution
                dout[x][y][filter] = kernel_conv(din, x, y, filter);
            }
        }
    }
}

/* CONV */
VALUE_TYPE kernel_conv(VALUE_TYPE din[CONV_IN_DIM_X][CONV_IN_DIM_Y], int x, int y, int filter) {
    /* Map x, y */
    int o_x = x * CONV_STRIDE;
    int o_y = y * CONV_STRIDE;

    VALUE_TYPE sum = 0;
    kernel_conv_label0: for (int i = 0; i < CONV_EXTFILTER; i++) {
    #pragma HLS pipeline
    #pragma HLS unroll

        kernel_conv_label1: for (int j = 0; j < CONV_EXTFILTER; j++) {
        	VALUE_TYPE f = conv_filter[filter][i][j];
        	VALUE_TYPE v = din[o_x + i][o_y + j];
            sum += f*v;
        }
    }

    if (sum < 0) {
    	return 0;
    }

    return sum;
}

```

**Relu Layer**
```python
if input > 0:
	return input
else:
	return 0
```

**Pool Layer**
```python
# Calculate the maximum value for each patch of the feature map.

for i from 0 to (x_max-x_w_width):
		for j from 0 to (y_max-y_w_width):
				out(i/x_w_width, j/y_w_width) = max in the window
				increment i by x_w_width
				increment j by y_w_width
		end for
end for
```

**Fully Connected**
![Alt text](/assets/images/fasionmnist-cnn-accel/FC.png))
```python
function fc_layer(input_image,output_classification):

	for n from 0 to number of classification:
		for I from 0 to input_image x dimension:
			for J from 0 to input_image y dimension:
				for Z from 0 to input_image z dimension:
					inputv = dot product of input_image[i][j][z] and fc weights
	
	# activation function
	output_classification[n] = sigmoid_function(inputv)
```

**Initial FC**
```c
fc_loop_4: for (int n = 0; n < 10; n++) {
float inputv = 0;
fc_loop_3: for (int i = 0; i < 12; i++) {
    fc_loop_2: for (int j = 0; j < 12; j++) {
        fc_loop_1: for (int z = 0; z < 32; z++) {
            int m = map(z, j, i);
            inputv += din[i][j][z] * fc_weights[m][n];
        }
    }
}
dout[n] = activator_function(inputv);
}
```

```c
float inputv[10] = {0};

fc_loop_3: for (int i = 0; i < 12; i++) {
  fc_loop_2: for (int z = 0; z < 32; z++) {
      fc_loop_1: for (int j = 0; j < 12; j++) {
      #pragma HLS pipeline
          int m = map(z, j, i);
          fc_loop_0 : for (int n = 0; n < 10; n++) {
              inputv[n] += din[i][j][z] * fc_weights[m][n];
          }
      }
  }
}


fc_activation_loop: for (int n = 0; n < 10; n++) {
  dout[n] = activator_function(inputv[n]);
}
```

## Opportunities for acceleration
1. Convolutional Layer
2. Relu layer
3. Pool layer
4. Fully Connected Layer

# Project Plan
Milestone 1 - Familiarisation and Project Setup
- Duration: week 5 - week 6
- Tasks:
 - Familiarise on CNN concepts
 - Experiement on simple python implementations

Milestone 2 - C/C++ Implementation
- Duration: week 7 - week 8
- Tasks:
 - Develop C/C++ implementation of the model
 - Benchmark and validate results

Milestone 3 - Optimisations with HLS
- Duration: Week 8 - Week 9
- Tasks:
 - Apply HLS directives to where suitable
 - Re-analyse design
 - Run HLS design on Zedboard (PS-PL)
 - Benchmark and compare

Milestone 4 - Finalisation
- Duration: week 9 - week 10
- Tasks:
 - Final presentation
 - Project report
 - Demo video

# Risk/Concern
The main risk and concern is time limitation for the project in this course offering. With the amount of time we have for the project we decided to leave the Conv2D layer to our extension work which was originally part of our model. If time allows, we will try and implement and optimise the additional layer. Current concerns also include how our HLS synthesized design is implementated on the FPGA and what data is interfaced between PS-PL (Do we run our optimised C/C++ code directly on PS and it would interface with PL? Or do we have to modify our C/C++ code to specifically use AXI to interface with the accelerator processor).