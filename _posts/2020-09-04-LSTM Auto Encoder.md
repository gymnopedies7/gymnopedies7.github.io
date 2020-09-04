---
title: "LSTM Auto Encoder"
categories:
  - 머신러닝
tags:
  - Keras
  - 모델
  - neural
  - 인공지능
  - AI
  - LSTM
  - Auto Encoder
  - Anomaly Detection
  - 이상감지
thumbnail: /assets/image/github.jpg
toc: True
toc_sticky: True
---


## Auto Encoder란?

신경망 모델로, Input을 암호화, 복호화하여 원래 Input에 가깝게 복원하는 모델이다.  
이 모델은 **Unsupervised** 이지만, Supervised 방식을 채택하여 학습한다.  **Self-supervised**라고도 함.  
이는 Input을 넣어 Input을 재생산하는것을 목표로 학습하기 때문이다.

## Encoder-Decoder LSTM Models

Long Short-Term Memory(LSTM)과 같은 Recurrent neural networks 는 특히 시계열 입력값에 대응하도록 설계되었다.  
LSTM은 과거 시계열 입력 정보를 사용하기 위해 내부 메모리를 사용한다.  
LSTM network는 Encoder-Decoder LSTM 이라 불리는 구조로 이루어져있다.    
이 구조는 Speech recognition과 text 번역같은 복잡한 시계열 예측문제에 장점을 가지고 있다.  


Encoder LSTM은 Input Sequence를 순서대로 읽고, 전체 Input sequence를 읽은 뒤에는
Hidden state 또는 output이 fixed-length 벡터로서 전체 입력 시퀀스의 내부 학습된 표현을 나타낸다.
이 벡터는 출력시퀀스의 각 단계가 생성될 때 이를 해석하는 Decoder 모델에 대한 입력으로 제공된다.


다만, 간단하게 만들어 낼 수 있는 Model에서는 직관적이고 빠르게 만들어낼 수 있어서 좋다.  
(왠만한 모델에는 다 적용할 수 있음)

## LSTM Autoencoder 란? 
위 두 개념, **Auto Encoder** + **Encoder-Decoder LSTM** 이다.  
**LSTM Autoencoder**  
  다시말해 Encoder-Decoder LSTM 구조를 이용하여 Autoencoder를 실행시킨 것이다.
{: .notice--info}

주어진 시퀀스 데이터셋에 대해 Encoder-Decoder LSTM은 Input 시퀀스를 읽고, Encode하고, Decode하고, Recreate한다.  
이 모델의 성능은 Input 시퀀스를 얼마나 잘 재생산(recreate)하는지에 달려있다.


시퀀스를 재생산하는 성능이 목표치 이상 달성하면, decoder파트는 제거되고, encoder 모델만 남겨진다.  
이 모델은 고정된 길이의 벡터로 Input 시퀀스를 encode하는데 사용된다.


