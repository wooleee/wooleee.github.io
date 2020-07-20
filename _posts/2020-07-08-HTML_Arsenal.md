---
title: "HTML Arsenal"
excerpt: "foo"
categories:
- Study
tags:
- HTML
- Study
last_modified_at: 2020-07-08
---
> **시작(To Commence)**

HTML 마크다운에 대해 파악하고자 HTML 무기고(Arsenal)를 작성해본다.
마크다운 문법은 __GFM__ 기준으로 작성했다.

Let us see simple grammer when writing HTML Markdown.  
All markdown grammer is based on __GFM__.
***
> **줄바꿈(Line Change)**  

마크다운은 스페이스 키를 친다고 해서 줄바꿈이 되지 않는다.  
줄을 바꾸려면, 라인 끝에서 **스페이스 키를 두번 쳐**야한다.

Markdown do not recognize line change by space.  
To change line, you should **tap spaces key twice** in the end of the line.
```
Sentence 1 <tap space key twice>  
Sentence 2
```
***
> **강조(Emphasize)**
>> *single asterisks*  

```
*single asterisks*
```

>> **double asterisks**
```
**double asterisks**  
```
  
>> ~~cancel line~~
```
~~cancel line~~
```
  
>> _single underscore_
```
_single underscore_
```

>> __double underscores__
```
__double underscores__
```
***
> **박스 만들기(Making Box for Text)**   

```
<table><tr><td>
<pre>
Put Content Here, Blah Blah
</pre>
</td></tr></table>
```

<table><tr><td>
<pre>
"행복이란 인간이 품고 있는 커다란 미망이다. 
신기루이다. 하지만 사람들은 그것을 깨닫지 못한다."
                     > 아르투르 쇼펜하우어 
</pre>
</td></tr></table>

***

> **텍스트 헤더(Text Header)**

# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
##### This is a H6


```
# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
##### This is a H6
```

***
> **인용**

> This is a first blockqute.
>> This is a second blockqute.
>>> This is a third blockqute.  
```
> This is a first blockqute.
>> This is a second blockqute.
>>> This is a third blockqute. 
```

***
> **분류(Classification, Indentation)**
1. FW
2. MF
3. DF
4. GK

```
1. FW
2. MF
3. DF
4. GK
```

* PL
  * 2019-2020 Champion
    * Manchester City FC

```
* PL
  * 2019-2020 Champion
    * Manchester City FC
```

***
> **파이썬 코드(Python Code)**

```python
s = "Whatever is Reasonable is True,\
and Whatever is True is Reasonable."
print s
```

```
```python
s = "Whatever is Reasonable is True,\
and Whatever is True is Reasonable."
print s```
```  
***
> **경계선 표시법(Boarder Line)**

```
***
```

***

> **링크 표시법 주소 임베디드(Links, address embeded)**  

[네이버](https://naver.com)
```
[네이버](https://naver.com)
```
***

> **링크 표시법 주소 표시(Links, address revealed)**   

 <https://naver.com>
```
<https://naver.com>
```
***
> **이미지 삽입(Add Images)** 

![](https://media1.tenor.com/images/c4251590126a92f1d4adaa5d590f4d04/tenor.gif?itemid=16405522)

```
![](https://media1.tenor.com/images/c4251590126a92f1d4adaa5d590f4d04/tenor.gif?itemid=16405522)
```

> **이미지 삽입 및 사이즈 편집(Add Images & Change Size of them)**   
width, height 파라미터를 활용하여 사이즈를 지정해주면 된다.

<img src="https://thumbs.gfycat.com/ThankfulFearlessHochstettersfrog.webp" width="100" height="100" alt="Photo of 3 cats">

```
<img src="https://thumbs.gfycat.com/ThankfulFearlessHochstettersfrog.webp" width="100" height="100" alt="Photo of 3 cats">
```

***
> **표 삽입(Add Tables)**  

>> **가운데 정렬(Add Tables, Centered)** 

| Food | Price | EA |
|:----|:----:|:----:|
| Ramyun | 800 won   | 10 |
| Snack | 900 won   | 20 |


```
| Food | Price | EA |
|:----|:----:|:----:|
| Ramyun | 800 won   | 10 |
| Snack | 900 won   | 20 |
```


>> **좌 정렬(Add Tables, Lefted)**  

| Food | Price | EA |
|:----:|:----|:----|
| Ramyun | 800 won   | 10 |
| Snack | 900 won   | 20 |

```
| Food | Price | EA |
|:----:|:----|:----|
| Ramyun | 800 won   | 10 |
| Snack | 900 won   | 20 |
```

***
> **주석 처리**  

```
<!--

여러줄 주석

-->
```
 
```
<! 한줄 주석>
```


--- 계속 업데이트 예정 ---