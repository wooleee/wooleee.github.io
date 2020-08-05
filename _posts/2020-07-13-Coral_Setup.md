---
layout: posts
title: "[TPU][한]Coral Setup"
excerpt: "구글에서 만든 엣지AI 구동을 위한 코랄 개발 보드 초기 셋팅법을 안내합니다(for 맥유저)"
published: True
categories:
- EdgeAI
  
tags:
- Study
- Coral
last_modified_at: 2020-07-13
---

## 시작하며..
구글은 작년 3월 Google Coral Development Board라는 소형 인공지능 디바이스를 출시했습니다. Edge AI를 활용하는 하드웨어의 탄생이라고 단순히 치부하기에는 클라우드나 로컬PC에서에서만 이루어지던 딥러닝이 분산되어서 시행하게 하는 어떻게 보면 분산 Deep Learning의 시초를 연 것입니다. 

> * Project using Hardware = All about its SETTINGS!*  

하드웨어를 동반하는 모든 프로젝트는 **셋팅**이 가장 고됩니다. Coral은 특히 출시된지 얼마 되지 않은 터라 Documentation이 친절하지 않구요. 딥러닝의 세계에 입문한지 반년도 되지 않은 본인의 Novice스러움을 백번 고려해도 어려웠습니다. 그래도 삽을 손에 들고 여러군데 파다보니 Documentation대로 구현을 하였고 이에 대해 단계별로 공유해 드립니다. 그래도 바이블은 바이블이니, 아래 링크를 클릭하면 구글의 공식 document를 확인할 수 있습니다.   
[Coral - Get started with the Dev Board](https://coral.ai/docs/dev-board/get-started)
![](https://coral.ai/static/docs/images/devboard/devboard-inhand.jpg)


## 구성품
구성품은 아래와 같습니다.
- *호스트 PC 1대*   
-- 코랄을 운용하고 코랄 내 OS 접속 및 운용을 도와주는 PC
- *구글 코랄보드 1대* 
- *[micro USB + USB C] to [USB] 케이블 1개*  
-- 호스트 PC와 코랄을 연결
- *[USB C] to [USB] 케이블 1개*   
-- 코랄 전원 공급용
- *wifi 연결*

> 카메라 모듈, USB Accelerator은 디플로이하고자 하는 모델에 따라서 선택적으로 사용!

## 본인 환경
- MacOS Catalina  (v10.15.5) 
###### 위 환경 중심으로만 서술할 예정입니다
###### (Win이나 Linux또는 Mac의 다른 OS에는 적용이 안될 가능성이 있습니다)

## 셋팅 시작
### 1. screen, fastboot 설치

#### 1.1. Install screen
screen을 설치합니다. screen은 mendel linux 기반의 코랄 OS화면을 호스트 PC를 통해 보고 명령할 수 있게 합니다.
```
$sudo apt-get install screen
```
#### 1.2. Install fastboot
fastboot을 설치합니다. fastboot은 말그대로 코랄을 boot해주는 역할을 합니다.  fastboot은 되도록 Latest 버젼을 다운 받도록 합니다. 아래 링크에서 Mac용 최신판을 다운받으면 됩니다. 다운받을 때 경로를 home/Downloads/ 에 지정합니다. 다운이 완료되면 파일을 unzip합니다.

[SDK 플랫폼 도구 다운](https://developer.android.com/studio/releases/platform-tools#downloads)

home/.local/bin에 새로운 디렉토리를 만듭니다.

```
$mkdir -p ~/.local/bin
```

unzip한 폴더를 새로만든 디렉토리에 옮깁니다.
```
$sudo mv ~/Downloads/platform-tools/fastboot ~/.local/bin/
```

fastboot의 버전을 확인합니다. 맥의 호환성을 위해 확인한 버전이 28.0.2이거나 최신이어야 합니다.
```
$fastboot --version
```

!! fastboot이 실행이 안된다면 본인의 shell(zsh, bash 등)환경에 새로만든 ~/.local/bin 경로가 지정이 안되어있기 때문입니다. ~/.zshrc파일(zsh의 경우), ~/.bash_profile(bash의 경우)을 열고 vi를 이용하여 아래 경로 추가 명령어를 기재하고 다시 시도해보면 됩니다.

```
$export PATH=~/.local/bin/:$PATH
```

### 2. fastboot  
먼저 확인하고 작업할 사항이 있습니다.
#### 2.0. 코랄 생산일  
코랄 생산일이 2019년 4월 10일 이전이면 아래와 같은 작업을 해야합니다.
![](https://coral.ai/static/docs/images/devboard/devboard-serialnumber-callouts.jpg)

##### year
 - Last digit of the year of manufacture: 0 - 9
##### month 
- Month of manufacture: 1 to 9 (Jan to Sep), A (Oct), B (Nov), C (Dec)
##### day 
- Day of manufacture: 01 to 31 (1st to 31st)


생산일이 9409(2019년 4월 9일)이거나 낮으면 아래 Port Driver의 업데이트가 필요합니다. 아래 링크에서 (맥용) 다운받고 설치를 진행하시면 됩니다.  
[CP210x USB to UART Bridge VCP Drivers](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers) **(본인은 생산일이 9410(2019년 4월 10일)이후의 코랄로 진행했음에도 이후 단계가 진행이 안되었고 혹시몰라서 아래 드라이버 설치를 하니 문제가 개선되었습니다. 즉, 생산일이 언제든 설치하시는 것을 권장합니다.)**


#### 2.1. 도킹(컴퓨터-코랄)
아래와 같이 호스트 PC본체와 코랄을 usb to micro usb 케이블로 연결합니다.
![](https://coral.ai/static/docs/images/devboard/devboard-serial-co.jpg)


#### 2.2. Screen 실행
(2.1.의 도킹이 된 채로)아래 명령어로 screen을 실행합니다.
```
$screen /dev/cu.SLAB_USBtoUART 115200
```
프롬프트 화면이 까맣게 질린다면(complete black) 2.3.로 가시면 됩니다.  
 [screen is terminating] 이라고 뜨거나 다른 메세지가 뜨면 오류인 것입니다.  
  그 경우 아래 두가지를 해보셔야 합니다.

```
물리적 도킹을 해제하고 다시 연결하고 명령어 다시 시행(될 때까지)
or
$screen -ls 를 쳐서 기존에 오픈된 session이 있는지 확인
```

#### 2.3. Screen 실행
아래와 같이 Power를 연결합니다. 충전어뎁터에 연결된 케이블 이용하여 usb c 위치에 꼽습니다. (어뎁터 뿐만 아니라 보조베터리로도 작동합니다.)


![](https://coral.ai/static/docs/images/devboard/devboard-serial-power-co.jpg)

잘 연결 됐다면 명령 프롬프트 화면에 수많은 명령어(u-boot prompt)가 한번에 주르륵 나열됩니다. Welcome 메세지도 확인 가능합니다. 
그리고 코랄보드의 fan이 돌아갑니다.  

이제 Coral 내의 디렉토리에 각종 모델을 적용하여 소형 인공지능을 구현할 수 있습니다. 모델 파라미터와 실행 파일 모두 Coral 로컬에서 관리하는 바 연산스피드는 탁월하며 보안 염려가 클라우드 기반 AI에 비해 적습니다.  

아래 링크를 클릭하시면 더 많은 어플리케이션 구현이 가능합니다.
<https://coral.ai>

끝.
