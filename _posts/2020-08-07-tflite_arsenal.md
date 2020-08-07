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

> See Coral's connection status
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

<img src = "/assets/img/hivemapper/fig1.png"><br>

* [Hivemapper](https://hivemapper.com/)<br>


* Led by **Ariel Seidman**, Hivemapper is a decentralized mapping network that enables monitoring and autonomous navigation without the need for expensive sensors, aircraft, or satellites.

> Hivemapper in 70 seconds
<iframe width="560" height="315" src="https://www.youtube.com/embed/Ap5mCUzpkls" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



# 1. Product
  
### 1.1. MAP
> Map, meet Analytics

<img src = "https://hivemapper.com/assets/images/marketing/map/Map-hero-2.png"><br>

* Powerful visualization and tools gives everyone the ability to quickly and easily get answers that move operations forward.

* Intergrates with comprehensive data of lidar, terrain and more. 
* Securely access and share maps from any web browser - no downloads or installs needed.

#### Features
<img src= "https://hivemapper.com/assets/images/marketing/map/unleash-map-search.png"><br>
* **Video Search** - Click anywhere in the map, and retrieve all videos of that location<br>


<img src= "https://hivemapper.com/assets/images/marketing/map/unleash-map-timeline.png"><br>
* **Timeline** - View a location at specific point in time and see how it has evolved<br>
  
<img src= "https://hivemapper.com/assets/images/marketing/map/unleash-map-heightabove.png"><br>
* **Height above ground** - Color the map by object height above ground. Identify obstructions for low-altitude aircraft and more.<br>
  
<img src= "https://hivemapper.com/assets/images/marketing/map/unleash-map-viewshed.png"><br>
* **Viewshed** - Determine visible and non-visible areas from a given point on your map, especially useful for positioning your cellular stations.<br>

<img src= "https://hivemapper.com/assets/images/marketing/map/unleash-map-measure.png"><br>
* **Measure** - Accurately measure and find coordinate information for any points on the map.<br>



#### Data Included  
* Streets and Points of Interest
* Terrain
* Lidar
* Uploaded Map Layers



### 1.2. CHANGE DETECTION
* Captures physical growth, loss, and disruptions faster than humans can.
* Augment human analysis with AI built directly into the map.
* Powerful filtering and sorting powered by Object AI.


#### Features
<img src= "https://hivemapper.com/assets/images/marketing/change-detection/Change-Detection-Feature-Hotspots-Main.png"><br>
* **Change Detection** -Video collections automatically generate change detection slices. Compare days to days, days to weeks, and even compare against historical lidar maps.<br>


<img src= "https://hivemapper.com/assets/images/marketing/change-detection/Change-Detection-Feature-Hotspots-Amount.png"><br>
* **Amount of change** - Filter detected changes by amount of change. See precise measurements for any spot.<br>
  
<img src= "https://hivemapper.com/assets/images/marketing/change-detection/Change-Detection-Feature-Hotspots-Before-After.png"><br>
* **Before and after videos** - Instantly retrieve before and after videos of any spot. Compare your changes with true to life imagery.<br>
  
<img src= "https://hivemapper.com/assets/images/marketing/change-detection/Change-Detection-Feature-Hotspots-Object.png"><br>
* **Filter by object** - Object AI allows you to filter your Change Detection map by object type like terrain, vegetation, and more.<br>

<img src= "https://hivemapper.com/assets/images/marketing/map/unleash-map-measure.png"><br>
* **Measure** - Accurately measure and find coordinate information for any points on the map.<br>

### 1.3. OBJECT AI
* Object AI understands whether the thing on a map is a building, vegetation, road, and more.
* Hivemapper harnessed AI to segment map by object type, making smart-maps accessible for all.
* Filter map and detected changes by the objects user care about, powered by AI.


#### Object Classes
<img src= "https://hivemapper.com/assets/images/marketing/object-ai/object_ai_02_buildings.png"><br>
* **Buildings**<br>


<img src= "https://hivemapper.com/assets/images/marketing/object-ai/object_ai_03_ground.png"><br>
* **Ground** - Natural ground such as dirt, rocks, sand, and grass.<br>
  
<img src= "https://hivemapper.com/assets/images/marketing/object-ai/object_ai_04_trees.png"><br>
* **Trees** <br>

<img src= "https://hivemapper.com/assets/images/marketing/object-ai/object_ai_05_mobile.png"><br>
* **Mobiles** - Objects that can move such as vehicles, boats, cars, airplanes, people, and animals.<br>

<img src= "https://hivemapper.com/assets/images/marketing/object-ai/object_ai_06_pavement.png"><br>
* **Pavement** <br>

#### Stanford Campus, CA. by Hivemapper 

<img src = "/assets/img/hivemapper/fig2.png"><br>
[Here](https://hivemapper.com/map?content=terrain&content=hmmap&content-filters=color%2Chighacc&gallery=stanford-campus&panel=living-map&view=-2700612.19%2C-4294063.05%2C3856778.24%2C-2.297%2C-1.553)<br>


# 2. How it Works
### 2.1. Collect Video
<img src = "/assets/img/hivemapper/fig3.png" width = "300"><br>
* Via any aircraft - Cessna, drone or helicopter
* Any Camera - GoPro, FLIR or Nikon
* Any Condition - Fly night or day, sunny or overcast. Hivemapper figures out

### 2.2. Upload/Build the Map
<img src = "https://hivemapper.com/assets/images/marketing/how-it-works/upload_screen_UI_hivemapper.png" width = "300">  

* Easy Uploader Tools - No desktop software to install. Just upload to Hivemapper.com
* Automated map creation - Hivemapper automatically takes the best parts of each video and turns them into a 3D map and Change Detection map.

### 2.3. Use Map produced by Hivemapper

(Described Above)
* Map - Powerful visualization and analytics built right into users' living map
* Change Detection - Smarter map automatically sees changes in the physical world and visualizes what is new, what is removed.
* Object AI - Automatically understands whether the thing on the map is a building, vegetation, road, and more.

# 3. Pricing
<img src = "/assets/img/hivemapper/fig4.png"><br>


# Z. Reference

- https://hivemapper.com/ 

<br><br>**The End.**