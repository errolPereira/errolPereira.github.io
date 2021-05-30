---
published: true
layout: post
title: How to Install CUDA and cuDNN on Ubuntu 20.04 LTS
---
In this post I will guide you in installing CUDA and cuDNN on your ubuntu machine.   


If you have NVIDIA graphics card in your system and want to use it to train machine learning and deep learning models, you need to first install the CUDA and cuDNN libraries in your system.  


![GeFroce NVIDIA]({{site.baseurl}}/images/christian-wiediger-3GUW88tRmv8-unsplash.jpg)
<center>Photo by <a href="https://unsplash.com/@christianw?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Christian Wiediger</a> on <a href="https://unsplash.com/s/photos/rtx?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a></center>


Below is my system configuration and the version of CUDA and cuDNN:  
OS 		: **Ubuntu 20.04 LTS**  
CUDA	: **10.2**  
cuDNN 	: **NA**  


Let's get started!


## Installing Pre-requisites

Before you install anything we need to make sure that the necessary graphics drivers are installed in the system. These drivers are required to communicate with the underlying graphics card.

Open the terminal by pressing cltr + alt + T and type the below command.

~~~~~~~~
nvidia-smi hello
~~~~~~~~

If the command returns a message saying "mvidia-smi" is not recognized by the system, then install nvidia-smi by running the below command:



If you do not get any ouput then run the next command to install the latest nvidia drivers in your system.
