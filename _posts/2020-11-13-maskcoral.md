---
layout: posts
title: "[Project]REAL-TIME MASK DETECTION ON GOOGLE EDGE TPU"
excerpt: "Non-designer designs the design of laboratory's symbol, interestingly."
published: False
categories:
- Project
tags:
- Project
last_modified_at: 2020-11-13
comments: false
author: "WooLee"
toc: True
---


**Table of Contents**<br>
* TOC
{:toc}

# REAL-TIME MASK DETECTION ON GOOGLE EDGE TPU
With the need in the era of COVID-19 spread all over the world, here we introduce real-time mask detector using Google Edge TPU. With high speed and decent accuracy, small-sized 150 dollar worth Google Coral supervises whether people in front of it wear mask properly or not.

<img src = "/assets/img/coral/coral.gif">
<p style="text-align:right;"><font size="2">&copy;	Team WSL(SNU GSDS)</font></p>


# The NEED
COVID-19 influences almost everything in our life in the globe. The simplist way to prevent deadlist disease is wearing mask. But, thing isn't going the way it should be. People, even in crowded and public area unwear mask or wear improperly. Mask detector then desperately needed for that.

# The IDEA
Mask detector, ok we need it but how? Is it accurate or even capture people wear mask around their chin? How about cost for the detector? How about the speed?

To resolve those worries, we conceived of deploying light application in the light AI model inferencing machine.

# The SOLUTION
With background study of image recognition, the optimal model for fullfilling the need was MobilenetV2+SSD. Using about 2000 images of people wearing/not wearing masks, we trained neural network with single layer, all at once(not multiple layer (e.g., detect person's face + detect mask)).

# The DETAIL
## Dataset
<img src = "/assets/img/coral/fig1.png">
<p style="text-align:right;"><font size="2">&copy;	Team WSL(SNU GSDS)</font></p>
We trained about 2000 images, containing both person wearing mask and not wearing mask. Decent accuracy has been accomplished due to the dataset of scale.


## Model Architecture
In transfer learning process, we did not freeze any layers in the base MobilenetV2 plus SSD model. We used batch size of 32. We used RMS Prop optimizer with initial learning rate of 0.04, momentum optimizer value of 0.9 and decaying at 0.9. The learning rate is also subject to exponential decaying schedule with decaying factor of 0.95 and decaying step of 800,720. We did quantization-aware training for quantized model and same hyperparameters were used for both models. Both models were trained for 50,000 epochs. 


## Conversion for Deploying to Google Coral
<img src = "/assets/img/coral/fig2.png">
<p style="text-align:right;"><font size="2">&copy;	Team WSL(SNU GSDS)</font></p>
Aforementioned, we used transfer learning process(MoblienetV2 + SSD) followed by quantization. Thanks to quantization, the inferencing speed was faster than we imagined with maintaining decent accuracy.

# Resources:
Further details can be found as follows;
- Find further in our [Github Page](https://github.com/KeondoPark/coral_mask)
- Deeply understand by referring the [Paper](https://arxiv.org/abs/2010.04427)
- Watch we deployed through [YouTube Demo Video](https://www.youtube.com/watch?v=XyWUv3Uxpz4&feature=youtu.be&ab_channel=WooLEE)
- Watch we present through [YouTube Presentation Video](https://www.youtube.com/watch?v=MdS2j5mPYmk&ab_channel=WooLEE)
- Proudly and Lastly, Korean Press named 'MK' introduced out project in the [News](https://mk.co.kr/news/it/view/2020/06/669932/)