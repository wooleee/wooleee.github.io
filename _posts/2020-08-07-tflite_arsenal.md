---
layout: posts
title: "[TPU]tflite Aresenal"
excerpt: "TensorflowLite & Coral Arsenal"
published: True
categories:
- EdgeAI
tags:
- Coral
- tflite
last_modified_at: 2020-08-07
comments: false
author: "WooLee"
---

This is TensorflowLite & Coral Arsenal. If flaw/the wrong is seen, please tell me. Sharing known and amending the wrong will make the world better place.

Before start, just refer to clumsy diagram how Coral, GIT, Host PC etc go. 
<img src = "/assets/img/tflite_arsenal/fig4.jpeg"><br>

# Coral Dev Board Operation
## Screen Access  

```
# mac
$screen /dev/cu.SLAB_USBtoUART 115200  
```

```
# linux
$sudo screen /dev/ttyUSB0 115200  
```
## Installing Packages
Installing packages in Coral is really coarse and hard. Kindly telling you cautions that pip, conda command would not work well. Representative package can be installed as below.

Go refer [git](https://github.com/google-coral/examples-camera) or follow below

Clone below git onto your coral
```
$mkdir google-coral && cd google-coral
$git clone https://github.com/google-coral/examples-camera.git --depth 1
```

Download the models
```
$cd examples-camera
$sh download_models.sh
```
These canned models will be downloaded and extracted to a new folder all_models.

Then run below to install packages.


* Raspicam -  Python example using picamera. This is only intended for Raspberry Pi and will require a Coral USB Accelerator. Use below to make sure all the dependencies are present.
```
$cd raspicam
$install_requirements.sh
```

* PyGame - Python example using pygame to obtain camera frames. Use below to make sure all the dependencies are present.
```
$cd pygame
$install_requirements.sh
```
* OpenCV -  Python example using OpenCV to obtain camera frames. Use below to make sure all the dependencies are present.

```
$cd opencv
$install_requirements.sh
```



## Connect to Internet
#### WIFI  
Coral is capable of connecting network through wifi.
Here is how it goes

Connect wifi
```
$nmtui
```

See Coral's connection status
```
$nmcli connection show
```

if Coral has connected well to wifi, wlan0 will display the wifi name According to below, 'GSDS3-5G' is the wifi name that Coral is connected on.  

```
NAME                UUID                                  TYPE      DEVICE 
gadget0             7048034a-2f04-4bea-9d6a-11bd40161e4f  ethernet  usb0   
gadget1             428afb89-7b67-4327-a3f9-7987e01a2776  ethernet  usb1   
GSDS3-5G            e2d321ce-579e-4e3e-8fdc-10a6902bf536  wifi      wlan0  
Wired connection 1  c9524701-9215-3a67-afc6-c182ca380ff2  ethernet  --
```


#### WIFI address 
If you've to run Coral, displayed in server, wifi address that Coral connects should be known in advance. Let's dig in.

IP Address Information search  

```
$ip addr show
```

* You can see below message. We want to know wifi address. Wifi address for 'wlan0'. In num 3, wlan0 info. is kindly shown. 
* We can know that wlan0 wifi address is 192.168.0.49. If you want to run coral(connected to wifi) in the server, you've got to note it.

```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc mq state DOWN group default qlen 1000
    link/ether 28:bd:89:bc:95:78 brd ff:ff:ff:ff:ff:ff
3: wlan0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 3000
    link/ether c4:ac:59:00:df:a7 brd ff:ff:ff:ff:ff:ff
    inet 192.168.0.49/24 brd 192.168.0.255 scope global dynamic noprefixroute wlan0
       valid_lft 6220sec preferred_lft 6220sec
    inet6 fe80::6c:ba74:c260:e97c/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
4: p2p0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 3000
    link/ether c6:ac:59:81:df:a7 brd ff:ff:ff:ff:ff:ff
5: usb0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc pfifo_fast state DOWN group default qlen 1000
    link/ether 02:22:78:0d:f6:df brd ff:ff:ff:ff:ff:ff
    inet 192.168.100.2/24 brd 192.168.100.255 scope global noprefixroute usb0
       valid_lft forever preferred_lft forever
    inet6 fe80::1192:64bc:8550:614c/64 scope link tentative noprefixroute 
       valid_lft forever preferred_lft forever
6: usb1: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc pfifo_fast state DOWN group default qlen 1000
    link/ether 02:22:78:0d:f6:de brd ff:ff:ff:ff:ff:ff
    inet 192.168.101.2/24 brd 192.168.101.255 scope global noprefixroute usb1
       valid_lft forever preferred_lft forever
    inet6 fe80::da9a:e8fc:b40c:3f09/64 scope link tentative noprefixroute 
       valid_lft forever preferred_lft forever
```

## git
> git install<br>

You can use git also in Coral. Remember, Coral is Linux OS based computer!

```
$apt-get source git
```
# Model Training
* If you trained the model, the output of model trained might as below
    * In case you used KERAS - '~.h5' format
    * In case you used tensorflow - '~.pb', '~.pbtxt' format

# Freeze the Graph


# Quantization
Quantization is process of make figures to INT8 format to run lightly in mobiles like Coral, iOS and Andriod device. Detailed theory can be found through Google Search.

## Through Tensorflow



## Through Bazel
#### Install Bazel
Install the latest version of Bazel as per the instructions on the [Bazel website](https://docs.bazel.build/versions/3.4.0/install.html).<br>
If you are mac user, homebrew is prerequisite.


#### Run Bazel and Quantize the Model

Go to dir to run Bazel
```
$cd tensorflow 
```

And run below command
```
! bazel run -c opt tensorflow/lite/toco:toco -- \
--input_file=${YOUR_DIR_THAT_PB_FILE_IS_IN}/~.pb \
--output_file=${YOUR_DIR_THAT_TFLITE_IS_TO_BE_SAVED}/~.tflite \
--input_shapes=1,320,320,3 \
--input_arrays=normalized_input_image_tensor \
--output_arrays='TFLite_Detection_PostProcess','TFLite_Detection_PostProcess:1','TFLite_Detection_PostProcess:2','TFLite_Detection_PostProcess:3'  \
--inference_type=QUANTIZED_UINT8 \
--allow_custom_ops \ 
```

Example will be,
```
! bazel run -c opt tensorflow/lite/toco:toco -- \
--input_file=/Users/woolee/mldl_project/github/coral_mask/1NN/mask_model_export_tflite6/tflite_graph.pb \
--output_file=/Users/woolee/mldl_project/github/coral_mask/1NN/mask_model_export_tflite6/one_nn.tflite \
--input_shapes=1,320,320,3 \
--input_arrays=normalized_input_image_tensor \
--output_arrays='TFLite_Detection_PostProcess','TFLite_Detection_PostProcess:1','TFLite_Detection_PostProcess:2','TFLite_Detection_PostProcess:3'  \
--inference_type=QUANTIZED_UINT8 \
--allow_custom_ops \ 
```


# Compile
## Through Jupyterhub
It's weird that Jupyterhub of local pc cannot execute compiler well. I recommend you do run it in GPU Server that has Jupyterhub. 

You got to have .tflite file to quantize and the environment of Jupyter Terminal is needed(if other method found, please tell us so that we can share!). Our reference [here](https://colab.research.google.com/github/google-coral/tutorials/blob/master/retrain_classification_ptq_tf1.ipynb#scrollTo=joxrIB0I3cdi).  


Upload Quantized tflite file into jupyterhub. Mine is named 'one_nn.tflite'
<img src = "/assets/img/tflite_arsenal/fig1.png"><br>

And open the jupyter terminal
<img src = "/assets/img/tflite_arsenal/fig2.png" width = "200"><br>


Go to Directory that .tflite is in.  
```
$cd ${YOUR_DIR_THAT_TFLITE_IS_IN}

# example #
$cd coral_mask
```

Run Below command **line by line** .It is the process of installing 'edgetpu-compiler'

```
! curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -

! echo "deb https://packages.cloud.google.com/apt coral-edgetpu-stable main" | sudo tee /etc/apt/sources.list.d/coral-edgetpu.list

! sudo apt-get update

! sudo apt-get install edgetpu-compiler	
```

And Compile the model

```
! edgetpu_compiler ${your_model_name}.tflite

# example #
! edgetpu_compiler one_nn.tflite
```

And finally,
<img src = "/assets/img/tflite_arsenal/fig3.png"><br>
In the same dir, name is the same but '_edgetpu' added will be seen. Here we can see file named 'one_nn **_edgetpu**.tflite'

It's all for compile process. Next, deploy the ~_edgetpu.tflite file together to your Coral device, so that Coral can utilize the quantized/complied tflite model.


# Deploy
To deploy the model, you have to clone the repo to your coral device. As model is '~_edgetpu.tfile' which is having label '~.txt', two files for running model should be in the directory of coral. So git clone them to your Coral.

## Server
https://coral.ai/docs/dev-board/camera/#using-a-streaming-server

> Run Coral(detection model) in Server  

Command(@Coral) is below:
```
! edgetpu_detect_server \
--model ${YOUR_DIR_THAT_TFLITE_FILE_IS_IN}/*.tflite \
--labels ${YOUR_DIR_THAT_TFLITE_LABEL_IS_IN}/*.txt
```

Example will be
```
! edgetpu_detect_server \
--model ~/coral_mask/1NN/mask_model_export_tflite6/one_nn_edgetpu.tflite \
--labels ~/coral_mask/1NN/mask_model_export_tflite6/one_nn_label.txt
```

If program run well, below will be shown, 
```
INFO:edgetpuvision.streaming.server:Listening on ports tcp: 4665, web: 4664, annexb: 4666
```

Then, you can see Coral is detecting or classifying through web. Go to browser(Google recommends Chrome), and access through wifi address plus port number(here, 4664).

```
xxx.xxx.x.xx:4664
```
Example will be
```
192.168.0.49:4664
```



# Z. Reference  

- https://coral.ai/docs/dev-board/camera/#using-a-streaming-server
- https://docs.bazel.build/versions/3.4.0/install.html
- https://github.com/google-coral/examples-camera
- https://colab.research.google.com/github/google-coral/tutorials/blob/-master/retrain_classification_ptq_tf1.ipynb#scrollTo=joxrIB0I3cdi


<br><br>**MAYBE The End or Still Updating**