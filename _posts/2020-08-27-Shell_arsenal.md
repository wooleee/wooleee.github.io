---
layout: posts
title: "[shell][한]Shell Arsenal / Shell 무기고"
excerpt: "Shell 운용하다가 구글 검색하느라 시간 쓰지 않는 것이 목표입니다."
published: True
categories:
- Arsenal
tags:
- shell
- command line
- terminal
- powershell
last_modified_at: 2020-08-27
comments: false
author: "WooLee"
toc: true

---

**Table of Contents**<br>
* TOC
{:toc}

Shell(이하 셸)은 OS마다 다른 고유명사를 가지고 있습니다. 윈도우는 PowerShell이고 맥에서는 Terminal.. <br>개발자(가 되기 원하는 사람으)로서 피할 수 없는 것이 바로 셸 입니다. <br>
손에 익어 문제없이 사용하는 분들이 제 주위 대다수이지만 배움이 느린 저는 이렇게 기록을 남길 필요를 느꼈습니다. <br>
자주 사용하는 커멘드는 사실 정해져있고 그 그룹이 크지 않아서, 오히려 자리에 앉아 파는 것 보다는 프로그램을 많이 운용해보는 것이 좋을 것 같습니다. 저는 이 글을 작성하며 소화하겠습니다.

**진행에 앞서** 명령칸에 <span style = "color:red"> \$ 나 >가 붙어있을 경우</span>  그 다음에 있는 구절만 쳐서 실행하면 됩니다.

예. 맥
```
$ mkdir mancity21plwinner
```

윈도우
```
> mkdir mancity21plwinner
```

라고 기재됐을 경우 셸에는 오직 mkdir mancity21plwinner 만 입력하고 엔터(return)하면 됩니다.

우선 디렉토리의 개념. 디렉토리는 간단히 우리가 흔히 아는 폴더라고 보면 됩니다. 셸을 운용하는 것을 쉽게 이하하기 위해 비유적으로, '껌뻑이는 명령어'를 '여러분'으로 생각하시고, '셸'은 '온갖 공간'으로 가정하면 됩니다.<br>여러분이 현 시점 집에 있든 카페에 있든 지금 어떠한 공간에 있죠? 껌뻑이는 명령어도 같은 상황입니다. 공간에도 위계가 있습니다. <br>
> 영화 테넷을 보러 CGV강남점에 간다고 쳤을 때 테넷을 상영하는 6관까지 가는데에 여러분은 많은 공간 위계를 지납니다. 우선 강남역 **스타플렉스**라는 건물에 가고 **5층**에서 티켓을 출력합니다. **6층**에 올라가 **6관**의 **I열**에 입장합니다.
> 이 경우 공간 위계는 [스타플렉스]-[cgv 5층|cgv 6층]-[6관]-[I열]이겠죠?

셸도 정확히 그러한 로직으로 운용하면 됩니다. 같은 명령어를 쳐도 셸의 작업 위치(pwd, 후술 예정)가 어디냐에 따라 에러를 뱉을 수도, 원하던 작업을 수행할 수도 있습니다.

## 1. 열기 / 닫기 
### 맥
- command + spacebar 클릭
- 서치바가 나오면 'terminal' 입력
- terminal 실행
 
### 윈도우
- start 클릭
- 프로그램 찾기 클릭하고 'powershell' 입력
- powershell 실행  

닫을 수도 있습니다 **exit**를 치면 닫을 수 있습니다.
```
$ exit
[Process Completed] # 이후에 셸은 운영이 안됩니다.
```  

꿀팁 하나, **clear**를 치면 위에있는 셸 스크립트 텍스트가 사라집니다(현재 디렉토리, 변수 등 다른 데이터는 유지됩니다 단지 **화면만 깨끗**해질 뿐)

## 2. 작업 위치 운영(pwd, cd)
- **pwd**는 **p**rint **w**orking **d**irectory의 약어 명령어로서 여러분이 어느 작업 위치에 있는지 알려주는 명령어입니다. 
- **cd**는 **c**hange **d**irectory의 약어 명령어로서 여러분이 어디 작업 위치로 간다고 선언하는 명령어입니다. 
<!-- > **pwd**로 여러분은 현재 '스타플렉스 6층 6관 I열'에 있음을 알것이고 **cd**로 여러분은 영화가 끝나고 '스타플렉스 지하1층 알라딘중고서점 외국 수필 섹션'으로 이동할 수 있을 것입니다.<br> -->

### 맥

Users라는 디렉토리안에 woolee 디렉토리가 있고 현재 셸의 작업 디렉토리는 woolee입니다.
```
$ pwd
/Users/woolee 
```

- ~ 를 붙이면 홈(디폴트) 디렉토리로 이동합니다. 
  - 맥은 /Users/{yourname} 이 홈 디렉토리입니다.
- 홈에 있는 디렉토리인 **mancity**로 가고 싶으면 명령어를 쳐서 이동할 수 있습니다. 
- 차상위 디렉토리로 가고 싶으면 뒤에 ..을 붙이면 됩니다.

저의 디바이스의 사용자 이름 즉 {yourname} 은 woolee임을 참고해주세요.

```
$ cd ~
/Users/woolee 

$ cd mancity
$ pwd
/Users/woolee/mancity

$ cd fw
$ pwd
/Users/woolee/mancity/fw

# 차상위 폴더로 가기
$ cd ..
$ pwd
/Users/woolee/mancity

# 차차상위 폴더로 가기
$ cd ../..
$ pwd
/Users/
$
```

### 윈도우
```
> cd ~
\Users\woolee 

> cd mancity
> pwd
Path
----
C:\Users\woolee\mancity

> cd fw
> pwd
Path
----
C:\Users\woolee\mancity\fw

# 차상위 폴더로 가기
> cd ..
> pwd
Path
----
C:\Users\woolee\mancity\

# 차차상위 폴더로 가기
> cd ..
> cd ..
> pwd
Path
----
C:\Users\

>
```

<!-- Linux
I'm assuming that if you have Linux then you already know how to get at your Terminal. Look through the menu for your window manager for anything named "Shell" or "Terminal." -->


## 3. 디렉토리 운영(ls, mkdir, rmdir)
- **ls**는 **l**i**s**t directory의 약어 명령어로서 현재 위치한 디렉토리 내의 디렉토리와 파일을 볼 수 있습니다.
- **mkdir**는 **m**a**k**e **dir**ectory의 약어 명령어로서 디렉토리를 만들 수 있습니다. 
- **rmdir**는 **r**e**m**ove **dir**ectory의 약어 명령어로서 디렉토리를 삭제할 수 있습니다. 

<!-- > **ls**로 여러분은 현재 '스타플렉스 6층 6관 I열'에 사람이 별로 없는 A, B, C열 그리고 달콤한 향의 팝콘을 먹는 뒷좌석에 사람 있음을 알것이고, **mkdir**로 늦게 온 친구를 영화관에 들어오게 할 수도 있고, **rmdir**로 뒷좌석 사람에게 팝콘  섭취하는 소리가 시끄러우니 나가서 드시고 오시라고 말할 수도 있습니다(예시가 다소 아스트랄 하네요. 무리한 비유욕은 이러한 결과를 낳습니다..)<br> -->

### 맥
```
(현재 작업위치 : /Users/woolee)
$ cd mancity
$ pwd
/Users/woolee/mancity
$ ls
manager fw mf df manchesterisred

$ cd manager
$ ls
pep.txt

$ cd ..
$ mkdir gk
$ ls
manager fw mf df manchesterisred gk

$ rmdir manchesterisred
$ ls
manager fw mf df gk

$ cd ..
$ pwd
/Users/woolee

$ mkdir mancity/manchesterisblue
$ cd mancity
$ ls
manager fw mf df gk manchesterisblue
$
```
> 맥의 경우 디렉토리 내에 하위 디렉토리, 파일 등 온갖 것이 없어야 rmdir 명령을 수용합니다. 지우고 싶은 디렉토리가 있는데, 그 하위 디렉토리, 파일도 지워도 상관없다 싶으시면 **$ rmdir -rf {디렉토리 path}** 로 지우시면 됩니다. '-'뒤에 붙는 알파벳은 셸 명령어의 세부조건이라고 보시면 됩니다. 후에 다룰 기회가 있으면 좋겠습니다.

### 윈도우
```
> cd mancity
> ls

    Directory: C:\Users\woolee\mancity


Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        10/26/1990   0:00 AM            manager
d----        10/26/1990   0:00 AM            fw
d----        10/26/1990   0:00 AM            mf
d----        10/26/1990   0:00 AM            df
d----        10/26/1990   0:00 AM            manchesterisred

> cd manager
> ls

    Directory: C:\Users\woolee\mancity\manager


Mode                LastWriteTime     Length Name
----                -------------     ------ ----
a----        10/26/1990   0:00 AM            pep.txt

> cd ..
> mkdir gk
> ls

    Directory: C:\Users\woolee\mancity


Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        10/26/1990   0:00 AM            manager
d----        10/26/1990   0:00 AM            fw
d----        10/26/1990   0:00 AM            mf
d----        10/26/1990   0:00 AM            df
d----        10/26/1990   0:00 AM            manchesterisred
d----        10/26/1990   0:00 AM            gk


> rmdir manchesterisred
> ls

    Directory: C:\Users\woolee\mancity


Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        10/26/1990   0:00 AM            manager
d----        10/26/1990   0:00 AM            fw
d----        10/26/1990   0:00 AM            mf
d----        10/26/1990   0:00 AM            df
d----        10/26/1990   0:00 AM            gk

> cd ..
> pwd
Path
----
C:\Users\woolee\
> mkdir mancity\manchesterisblue


> cd mancity
> ls

    Directory: C:\Users\woolee\mancity


Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        10/26/1990   0:00 AM            manager
d----        10/26/1990   0:00 AM            fw
d----        10/26/1990   0:00 AM            mf
d----        10/26/1990   0:00 AM            df
d----        10/26/1990   0:00 AM            gk
d----        10/26/1990   0:00 AM            manchesterisblue

>
```

## 4. 파일 운영 (touch(new item), cp, mv, rm)

(맥 기준)
- **touch**는 현재 위치한 디렉토리에 파일을 만들 수있습니다.(윈도우: **new-item**)
- **cp**는 **c**o**p**y 약어 명령어로서 디렉토리를 복사-붙여넣기할 수 있습니다.
- **mv**는 **m**o**v**e 약어 명령어로서 디렉토리를 이동(잘라내기-붙여넣기)할 수 있습니다.

```
$ pwd
/Users/woolee
$ cd mancity/fw
$ pwd
/Users/woolee/mancity/fw

$ ls
aguero.txt mahrez.txt jesus.txt ederson.txt

$ touch messi.txt
$ ls
aguero.txt mahrez.txt jesus.txt ederson.txt messi.txt

# messi.txt라는 파일을 messi2.txt로 복사합니다(명령시에 messi2.txt 파일은 존재하지 않아도 됨)
$ cp messi.txt messi2.txt
$ ls
aguero.txt mahrez.txt jesus.txt ederson.txt messi.txt messi2.txt

# messi2.txt 삭제
$ rm messi2.txt
$ ls
aguero.txt mahrez.txt jesus.txt ederson.txt messi.txt

$ pwd
/Users/woolee/mancity/fw


# 현재 작업위치의 messi.txt를 홈/mancity/trans_in로 복사합니다.
$ cp messi.txt ~/mancity/trans_in
$ cd ../trans_in 
$ ls
messi.txt

# 홈/mancity/fw의 ederson.txt를 홈/mancity/gk 디렉토리로 이동합니다.
$ mv ~/mancity/fw/ederson.txt ~/mancity/gk/ederson.txt

$ cd ~/mancity/gk
$ ls
bravo.txt ederson.txt

$ cd ~
$ pwd
/Users/woolee
$
```
- 어느정도 파일의 이동은 파악이 되셨나요? 복사, 이동 기능은 '디렉토리' 단위도 가능합니다. 
- 맥북은 슬래시(/)로 디렉토리의 정체성을 파악합니다. 텍스트 뒤에 /가 없으면 디렉토리로 고려합니다. cp -R mancity/ mcfc/ 를 입력하면 에러를 낼 것입니다.
- 디렉토리와 그의 하위 디렉토리 및 파일을 옮기고 싶으면 cp뒤에 -R을 붙이면 됩니다.<br>
  
```
$ cp -R mancity mcfc
$ ls
mancity mcfc

$ mv mcfc mancity
$ ls
mancity
$
```

### 윈도우
```
> pwd
Path
----
C:\Users\woolee\

> cd mancity/fw
> pwd
Path
----
C:\Users\woolee\mancity\fw

> ls

    Directory: C:\Users\woolee\mancity\fw

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
a----        10/26/1990   0:00 AM            aguero.txt
a----        10/26/1990   0:00 AM            mahrez.txt
a----        10/26/1990   0:00 AM            jesus.txt
a----        10/26/1990   0:00 AM            ederson.txt


> New-Item messi.txt -type file

> ls

    Directory: C:\Users\woolee\mancity\fw

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
a----        10/26/1990   0:00 AM            aguero.txt
a----        10/26/1990   0:00 AM            mahrez.txt
a----        10/26/1990   0:00 AM            jesus.txt
a----        10/26/1990   0:00 AM            ederson.txt
a----        10/01/2020   0:00 AM            messi.txt


# messi.txt라는 파일을 messi2.txt로 복사합니다(명령시에 messi2.txt 파일은 존재하지 않아도 됨)
> cp messi.txt messi2.txt
> ls

    Directory: C:\Users\woolee\mancity\fw

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
a----        10/26/1990   0:00 AM            aguero.txt
a----        10/26/1990   0:00 AM            mahrez.txt
a----        10/26/1990   0:00 AM            jesus.txt
a----        10/26/1990   0:00 AM            ederson.txt
a----        10/01/2020   0:00 AM            messi.txt
a----        10/01/2020   0:00 AM            messi2.txt


# messi2.txt 삭제
> rm messi2.txt
> ls

    Directory: C:\Users\woolee\mancity\fw

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
a----        10/26/1990   0:00 AM            aguero.txt
a----        10/26/1990   0:00 AM            mahrez.txt
a----        10/26/1990   0:00 AM            jesus.txt
a----        10/26/1990   0:00 AM            ederson.txt
a----        10/01/2020   0:00 AM            messi.txt


# 현재 작업위치의 messi.txt를 홈/mancity/trans_in로 복사합니다.
> cp messi.txt ~\mancity\trans_in
> cd ..\trans_in 
> ls

    Directory: C:\Users\woolee\mancity\trans_in


Mode                LastWriteTime     Length Name
----                -------------     ------ ----
a----        10/01/2020   0:00 AM            messi.txt


# 홈/mancity/fw의 ederson.txt를 홈/mancity/gk 디렉토리로 이동합니다.
> mv ~\mancity\fw\ederson.txt ~\mancity\gk\ederson.txt
> cd ..\gk
> ls

    Directory: C:\Users\woolee\mancity\gk


Mode                LastWriteTime     Length Name
----                -------------     ------ ----
a----        10/26/1990   0:00 AM            bravo.txt
a----        10/01/2020   0:00 AM            ederson.txt

> cd ~
> pwd
Path
----
C:\Users\woolee\
>
```


rm 명령에 뒤에 쓸만한 설정
- \- Force : 파일/폴더에 읽기 속성이 있는 경우 강제로 명령어 실행
- \- Recurse : 재귀를 통해 지정된 폴더 내부 모두를 복사/삭제/이동 처리


## 5. 파일 조망 (less, cat)

(맥 기준)
- **less**는 파일의 내용을 새 화면에서 열람할 수 있습니다. 하지만, vi처럼 파일을 편집할 수 있지는 않습니다. (윈도우: **more**) 전환된 새 화면에서 나가고자 하시면 영문키 q를 치고 원화면으로 회귀하면 됩니다.
- **cat**는 파일의 내용을 셸 화면에 프린트할 수 있습니다.

- **less**는 쉬는시간의 친구의 필기노트를 잠시 빌려 내용을 살피고(편집은 X) 노트를 돌려주는 것이라면 **cat**은 필기노트를 빌려 내 노트에 그대로 옮겨쓰고(프린트) 노트를 돌려주는 것이라고 생각하면 쉬울 것 같습니다.

### 맥
```
$ pwd
/Users/woolee
$ cd fw

$ less messi.txt
#####Content is Displayed#####
Born in 1987 June 24
Argentina
Left foot
FC Barcelona(2004~)
messi.txt (END)
$ q
##############################


$ cat messi.txt
Born in 1987 June 24
Argentina
Left foot
FC Barcelona(2004~)
messi.txt (END)
```

### 윈도우
```
> pwd
Path
----
C:\Users\woolee\

> cd fw
> more messi.txt
#####Content is Displayed#####
Born in 1987 June 24
Argentina
Left foot
FC Barcelona(2004~)
messi.txt (END)
> q
##############################


> cat messi.txt
Born in 1987 June 24
Argentina
Left foot
FC Barcelona(2004~)
messi.txt (END)
>
```
## Y. 퀵시트
### 리눅스/맥

명령어(약어) - 전체이름  / 설명
pwd - print working directory / 현재 작업 디렉토리 보기
hostname - my computer's network name / 작업 컴퓨터의 네트워크명
mkdir - make directory / 디렉토리 만들기
cd - change directory / 작업 디렉토리 바꾸기
ls - list directory / 디렉토리 리스트 보이기
rmdir - remove directory / 디렉토리 지우기
pushd - push directory / 디렉토리 밀기(?)
popd - pop directory / 디렉토리 뽑기(?)
cp - copy a file or directory / 디렉토리 복사하기
mv - move a file or directory / 디렉토리 옮기기
less - page through a file / 
cat - print the whole file / 파일 요약내용 열람
xargs - execute arguments / 아그먼트 실행
find - find files / 파일 찾기
grep - find things inside files
man - read a manual page
apropos - find what man page is appropriate
env - look at your environment
echo - print some arguments
export - export/set a new environment variable
exit - exit the shell
sudo - em-super-powered

### 윈도우

명령어(약어) - 전체이름  / 설명
pwd - print working directory
hostname - my computer's network name
mkdir - make directory
cd - change directory
ls - list directory
rmdir - remove directory
pushd - push directory
popd - pop directory
cp - copy a file or directory
robocopy - robust copy
mv - move a file or directory
more - page through a file
type - print the whole file
forfiles - run a command on lots of files
dir -r - find files
select-string - find things inside files
help - read a manual page
helpctr - find what man page is appropriate
echo - print some arguments
set - export/set a new environment variable
exit - exit the shell
runas - em-super-powered

# Z. 참조  

- https://sacstory.tistory.com/entry/PowerShell-기초-명령어-복사-삭제-이동

- https://ko.wikipedia.org/wiki/%ED%8C%8C%EC%9B%8C%EC%85%B8

<br><br>**계속 업데이트 예정**