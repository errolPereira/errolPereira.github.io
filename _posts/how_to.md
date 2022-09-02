---
published: true
layout: post
title: How to create custom object detection model using Tensorflow Object Detection API
---
In this post I will guide you in creating a custom object detection model using Tensorflow's  Object detection API.

After completing this tutorial, you will know:

1. Install TFOD2 with GPU
2. Prepare and annotate image data for custom object detection
3. Configure a model from TFOD model zoo
4. Train and test the model

In this post I am using Ubuntu machine to install the package and train object detection model. Below are the specifications of my machine and the libraries I am going to use.

- OS : Ubuntu 20.04 LTS
- Python : 3.9
- Tensorflow : 2.9.0
- TFOD : v2

## Installing Tensorflow Object Detection API with GPU

If you haven't installed tensorflow with GPU enabled yet please check out my [post](https://errolpereira.github.io/how-to-install-CUDA-and-cuDNN-on-ubuntu/){:target="_blank" rel="noopener"} to install it. I have also provided a bash script which will take care of the installation for you.

Once tensorflow is installed on your system and you have tested it on yur GPU machine we will go ahead installing the object detection API of tensorflow.

First, clone the tensorflow object detection model repository in your local system from this [repo](https://github.com/tensorflow/models){:target="_blank" rel="noopener"}.

After cloning the repository, install the protobuff library using the below commands. If you haven't activated your conda environment yet, now is a good time to activate it.

<p style="background-color:#f2f2f2; padding:10px;"><code>conda activate tensorflow</code></p>
<p style="background-color:#f2f2f2; padding:10px;"><code>sudo apt install protobuf-compiler</code></p>
<p style="background-color:#f2f2f2; padding:10px;"><code>pip3 install cython
</code></p>
<p style="background-color:#f2f2f2; padding:10px;"><code>pip3 install pycocotools
</code></p>

After the protobuff library is installed cd into your **TF_repo_PATH/model/research** folder and run the below command.

<p style="background-color:#f2f2f2; padding:10px;"><code>protoc object_detection/protos/*.proto --python_out=.</code></p>

The above command will not produce any output. The next dependency of TFOD is the COCO API installation. For this first clone the coco repository in a folder outside your models folder. After cloning the repo, build the coco API using the below commands and then copy the pycocotools folder generated after the build in the **model/research/** folder.

<p style="background-color:#f2f2f2; padding:10px;">
  <code>git clone https://github.com/cocodataset/cocoapi.git.</code>
  <code>cd cocoapi/PythonAPI</code>
  <code>make</code>
  <code>cp -r pycocotools PATH_TO_TF/TensorFlow/models/research/</code>
</p>

Once the coco API installation is done, we will move on to setup and install the objection detection library in the conda environement. Run the below commands from the  research folder to start the installation.

<p style="background-color:#f2f2f2; padding:10px;">
  <code>cp object_detection/packages/tf2/setup.py .</code>
  <code>python -m pip install --use-feature=2020-resolver .</code>
</p>

# Testing the object detection API

Now that we have installed the API in our system, let's go ahead and test it. Run the below command that will trigger a chain of tests performed using one of the models from the Tensorflow Model Zoo and will show a similar output as below. The command needs to be run from the research folder.

<p style="background-color:#f2f2f2; padding:10px;"><code>python object_detection/builders/model_builder_tf2_test.py</code></p>

