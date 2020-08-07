---
layout: posts
title: "[TPU]From DL Model to Mobile Device"
excerpt: "tflite Arsenal - Sapjil while doing TFLITE things"
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

```
$
```

# Coral Dev Board Operation
## Installing Packages
#### Pygame
#### OpenCV

# mac
```
$ screen /dev/cu.SLAB_USBtoUART 115200  
```

```
# linux
$ sudo screen /dev/ttyUSB0 115200  
```

## Connect to Internet
#### wifi  
Coral is capable of connecting network through wifi.
Here is how it goes

> Connect wifi
```
$nmtui
```

> See Coral's connection status<br>
```
$nmcli connection show
```

> if Coral has connected well to wifi, wlan0 will display the wifi name.
```
NAME                UUID                                  TYPE      DEVICE 
gadget0             7048034a-2f04-4bea-9d6a-11bd40161e4f  ethernet  usb0   
gadget1             428afb89-7b67-4327-a3f9-7987e01a2776  ethernet  usb1   
GSDS3-5G            e2d321ce-579e-4e3e-8fdc-10a6902bf536  wifi      wlan0  
Wired connection 1  c9524701-9215-3a67-afc6-c182ca380ff2  ethernet  --
```


#### wifi address 
If you've to run Coral, displayed in server, wifi address that Coral connects should be known in advance. Let's dig in.

> IP Address Information search
```
$ip addr show
```

You can see
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

# Model Training

# Freeze the Graph


# Quantization
## Through Tensorflow
## Through Bazel
#### Install Bazel
#### Run Bazel and Quantize the Model

# Compile
## Through Jupyterhub

# Deploy
## Server
## HDMI Cable

# Z. Reference

- 

<br><br>**The End.**