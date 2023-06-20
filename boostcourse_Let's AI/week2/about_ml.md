# 딥러닝이란? & 딥러닝의 역사

## Introduction

What make you a good deep learner?

1. Implementation Skills
2. Math Skills (Linear Algebra, Probability)
   - 선형대수학, 확률론
3. Knowing a lot of recent Papers
   - 트렌드와 연구결과!

## Key Components of Deep Learning

- The **data** that the model can learn from
- The **model** how to transform the data
- The **loss** function that quantifies the badness of the model
- The **algorithm** to adjust the parameters to minimize the loss

### Data

Data depend on the type of the problem to solve.

### Model

ex) AlexNet, GoogLeNet, ResNet, DenceNet, LSTM, Deep AutoEncoders, GAN…

### Loss

The loss function is a proxy of what we want to achieve.

### Optimization Algorithm

Data, Model, Loss가 모두 정해져 있는 상황에서 네트워크를 줄이는 방법

## Historical Review

- 2012 - AlexNet
  - 이미지 분류를 목적으로 함.
  - 딥러닝이 실질적으로 성능을 발휘하기 시작함.
- 2013 - DQN
  - 알파고를 만든 회사가 만든 방법론.
- 2014 - Encoder / Decoder
  - NMT (신경망 기계 번역 - Neural machine translation) 문제를 풀기 위함.
  - 기계어 번역의 트렌드에 크게 영향.
- 2014 - Adam Optimizer
  - 딥러닝을 학습시키기 위한 용도로 주로 사용.
  - 결과가 매우 우수.
- 2015 - Generative Adversarial Network
  - 이미지, 텍스트를 만들어내는 것.
- 2015 - Residual Networks
  - 네트워크를 깊게 쌓아도 성능을 좋게 만들어줌.
- 2017 - Transformer
- 2018 - BERT (fine-tuned NLP models)
  - Bidirectional Encoder Representations from Transformers
- 2019 - BIG Language Models
  - ex) GPT3: 175억개의 parameters로 된 모델
- 2020 - Self Supervised Learning
  - 주어진 학습데이터 외 라벨을 모르는 unsupervised data를 활용하겠다는 것.
  - SimCLR: a simple framework for contrastive learning of visual representations
