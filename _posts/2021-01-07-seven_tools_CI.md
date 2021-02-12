---
layout: posts
title: "[CI]The Seven tools of Causal Inference with Reflections on Machine Learning"
excerpt: "By J.Pearl"
published: False
categories:
- Causal_Inference
tags:
- Causal_Inference
last_modified_at: 2021-01-07
comments: false
author: "WooLee"
toc: True
---


**Table of Contents**<br>
* TOC
{:toc}

<details>
  <summary>원문</summary>
  The dramatic success in machine learning has led to an explosion of AI applications and increasing expectations for autonomous systems that exhibit human-level intelligence. These expectations, however, have met with fundamental obstacles that cut across many applica- tion areas. One such obstacle is adaptability or robustness. Machine learning researchers have noted that current systems lack the capa- bility of recognizing or reacting to new circumstances they have not been specifically programmed or trained for. Intensive theoretical and experimental efforts toward “transfer learning,” “domain adap- tation,” and “Lifelong learning” [Chen and Liu 2016] are reflective of this obstacle.
</details>

머신러닝의 엄청난 성장은 수많은 AI 어플리케이션 제품을 낳았고, 사람 수준의 지능을 능가하는 자동화된 시스템에 대한 인류의 기대를 한층 높여놓았다. 하지만, 머신러닝이 가지는 근본적인 문제점인 적응성, 강건성 등의 한계가 금방 노출되었고, 새로운 데이터와 새로운 환경에 대응할만한 모델을 만드는 데에 수많은 전문가가 고군분투를 하고 있다. 집약적이고 이론적인 실험 즉 "Transfer Learning", "Domain Adaptation" 그리고 "LifeLong Learning"이 그 예시다. 

<details>
  <summary>원문</summary>
  Another obstacle is explainability, that is, “machine learning mod- els remain mostly black boxes” [Ribeiro et al. 2016] unable to ex- plain the reasons behind their predictions or recommendations, thus eroding users trust. and impeding diagnosis and repair. See [Marcus 2018] and ⟨http://www.sciencemag.org/news/2018/05/ai- researchers-allege-machine-learning-alchemy⟩.
A third obstacle concerns the understanding of cause-effect con- nections. This hallmark of human cognition [Lake et al. 2015; Pearl and Mackenzie 2018] is, in this author’s opinion, a necessary (though not sufficient) ingredient for achieving human-level intelligence. This ingredient should allow computer systems to choreograph a parsimonious and modular representation of their environment, interrogate that representation, distort it by acts of imagination and finally answer “What if?” kind of questions. Examples are interven- tional questions: “What if I make it happen?” and retrospective or explanatory questions: “What if I had acted differently?” or “what if my flight had not been late?” Such questions cannot be articulated, let alone answered by systems that operate in purely statistical mode, as do most learning machines today.
</details>

다른 장애물은 '설명가능성'이다. 즉, 머신러닝이 답하는 예측치, 추천결과값등이 당최 왜 그런지 이유를 설명치 못하는 소위 블랙박스 문제는 사용자의 신뢰를 갉아먹고, 소상한 진단과 모델 수정이 어렵게 만든다. 마지막으로 가장 중요한 장애물은 원인-결과 연결성에 관해서다. 인간 인지의 가장 큰 부분인 원인-결과 분석 가능성은 필자의 개인적인 견해로는, 완전한 인간수준의 AI를 만들어내는데에 필요 조건이라고 생각한다(i.e., 인간수준 AI는 필연적으로 원인-결과 분석 능력이 있다)(not 충분 조건 (원인-결과 분석 능력이 있으면 필연적으로 인간수준 AI에 도달한다.)). 그래야만 컴퓨터 시스템이 추가적인 고도의 컴퓨팅이 없이도 인과관계에 의한 케이스들을 조합해서 시연할 수 있고 결국 "만약.. 라면?"이라는 물음도 답을 할 수 있을 것이다. 중재물음(intervention question): "내가 그렇게 꼭 일어나게 만든다면..?" 과 설명이 필요한 물음, 과거를 회상하는 물음:"내가 다르게 행동했다면..?", "내 비행기가 연착되지 않았다면..?"이 그 예시이다. 순수 머신러닝 기법으로, 오직 통계학적 방법론만으로는 위 물음들에 대한 해답을 찾기는 쉽지 않다.


<details>
  <summary>원문</summary>
  I postulate that all three obstacles mentioned above require equip- ping machines with causal modeling tools, in particular, causal diagrams and their associated logic. Advances in graphical and structural models have made counterfactuals computationally man- ageable and thus rendered causal reasoning a viable component in support of strong AI.

  In the next section, I will describe a three-level hierarchy that re- stricts and governs inferences in causal reasoning. The final section summarizes how traditional impediments are circumvented using modern tools of causal inference. In particular, I will present seven tasks which are beyond reach of associational learning systems and which have been accomplished using the tools of causal modeling.

</details>

나는 위에 소개한 문제점들이 연역 모델링 도구 특히 연역 Diagram 그리고 연관된 논리에 의해 해결이 되어야 함을 짚을 것이다. 구조적이고 그래프


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