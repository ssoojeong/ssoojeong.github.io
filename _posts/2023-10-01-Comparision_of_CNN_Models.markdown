---
layout: post
title:  "Comparision of CNN Models"
date:   2023-10-01 18:05:55 +0300 
image:  alexnet.png
tags:   Study
---

## &#x1F4E2; Project Overview: 2310~2311
### 주요 기능 
- 대표적인 4가지 CNN 모델 (AlexNet, VGG, GoogLeNet, ResNet) 성능 비교
- PyTorch를 활용하여 CIFAR-10 데이터셋에서 Classificaation 성능 실험

### [View Project & Code](https://github.com/ssoojeong/Comparision_of_CNN_Models.git)

----

### &#x1F31F; CNN 모델 리스트
<table border="1">
  <thead>
    <tr>
      <th>모델</th>
      <th>발표 연도</th>
      <th>발표 학회</th>
      <th>논문 제목</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>AlexNet</b></td>
      <td>2012년</td>
      <td>NIPS (NeurIPS)</td>
      <td><i>ImageNet Classification with Deep Convolutional Neural Networks</i></td>
    </tr>
    <tr>
      <td><b>VGG</b></td>
      <td>2014년</td>
      <td>ICLR</td>
      <td><i>Very Deep Convolutional Networks for Large-Scale Image Recognition</i></td>
    </tr>
    <tr>
      <td><b>GoogLeNet</b></td>
      <td>2014년</td>
      <td>CVPR</td>
      <td><i>Going Deeper with Convolutions</i></td>
    </tr>
    <tr>
      <td><b>ResNet</b></td>
      <td>2015년</td>
      <td>CVPR</td>
      <td><i>Deep Residual Learning for Image Recognition</i></td>
    </tr>
  </tbody>
</table>

<p><br></p> <!-- 줄바꿈 추가 -->

### 1. AlexNet (2012, NeurIPS)
<img src="../images/alexnet.png" alt="AlexNet Model" width="500">

- 딥러닝의 대표적인 모델로, ReLU 활성화 함수와 Dropout을 도입하여 학습 성능을 크게 개선함.  
- 대규모 데이터셋(ImageNet)에서 우수한 성능을 보여주며, GPU를 활용한 병렬 처리를 최초로 시도한 모델. 
- 이 모델은 딥러닝 시대를 열었다고 평가받으며, 컨볼루션 신경망(CNN)의 효율성을 증명함.

<p><br></p> <!-- 줄바꿈 추가 -->

### 2. VGG (2014, ICLR)
<img src="../images/vgg.png" alt="VGG Model" width="500">

- 3x3 컨볼루션 필터를 반복적으로 사용하여 간단하면서도 깊은 구조를 가진 네트워크.
- 모델의 깊이에 따라 VGG-16, VGG-19 등으로 나뉘며, ImageNet 대회에서 상위권 성능을 기록함.
- 네트워크가 깊어질수록 성능이 향상되지만, 계산량이 많이 늘어나는 단점이 있음.

<p><br></p> <!-- 줄바꿈 추가 -->

### 3. GoogLeNet (2014, CVPR)
<img src="../images/googlenet.png" alt="googlenet Model" width="500">

- Inception 모듈을 활용하여 여러 크기의 필터를 병렬로 적용, 다양한 특징을 추출할 수 있습니다.  
- 네트워크 깊이와 계산 효율성을 모두 고려하여 설계된 모델로, ImageNet 대회에서 높은 성능을 기록함.
- 모델 크기가 비교적 작아 실제 환경에서도 효과적으로 사용될 수 있음.

<p><br></p> <!-- 줄바꿈 추가 -->

### 4. ResNet (2015, CVPR)
<img src="../images/resnet.png" alt="resnet Model" width="500">

- Residual Block을 도입하여 매우 깊은 네트워크의 학습이 가능함.  
- "Identity Mapping"을 활용해 기울기 소실 문제를 해결하며, 학습 안정성과 성능을 동시에 확보함.
- 152층 네트워크로 ImageNet 대회를 우승하며 딥러닝 모델의 한계를 극복함.

---

### 🧪 평가 지표
- Accuracy (정확도): 이미지 분류 정확도
- Trian Time (소요시간/에폭): 한 에폭당 소요된 시간

---

### 📝 데이터셋
#### CIFAR-10
<img src="../images/cifar10.png" alt="cifar10 dataset" width="500">

- 10개의 클래스
- 32x32 컬러 이미지
- Train dataset: 50,000장
- Test dataset: 10,000장

----

### 💻 실험 방법

#### 1. 가상 환경 설정

```bash
conda create -n cnns python=3.9
conda activate cnns

pip install -r requirements.txt
```
<p><br></p> <!-- 줄바꿈 추가 -->

#### 2. 모델 훈련 및 인퍼런스
```bash
# 1. GLIDE
python train.py \
    --model {모델명} \ #e.g., alexnet, vgg16 ... \
    --epochs 10 #defualt: 25
    --gpus 0 \
```
<p>
  <strong>모델명</strong>: 
  <code>resnet18</code>, 
  <code>resnet50</code>, 
  <code>vgg16</code>, 
  <code>alexnet</code>, 
  <code>inception_v3</code>, 
  <code>googlenet</code>, 
  <code>mobilenet_v2</code>, 
  <code>densenet121</code>
</p>

<p><br></p> <!-- 줄바꿈 추가 -->

#### 3. 모델 학습 log 및 성능 확인
log 저장 경로: ```./results/log/```

```bash
#e.g., AlexNet, 25epoch

############학습 시작############
Epoch 0/24
----------
train Loss: 9.1037 Acc: 0.1560
val Loss: 11.9101 Acc: 0.1925
Epoch 1/24
----------

...

############학습 끝############
Training complete in 3m 28s
Best val Acc: 0.449057
```

---

### 📄 프로젝트 요약 보고서

대표적인 합성곱 신경망 모델의 비교
📄 [Report](https://drive.google.com/file/d/1iBT7kGLWwPyjr7raycYI1txU9_4eN2Ud/view?usp=sharing)

Comparision of representive Convolution Neural Network models

(권하연, 김소정, 배인우, 이강은)
