---
layout: post
title:  "Style Transfer SOTA Models"
date:   2024-11-20 18:05:55 +0300
image:  sota/comparison.png
tags:   Project
---

## &#x1F4E2; Project Report Overview
### 📄 프로젝트 개요
- 최신 Style Transfer 모델을 비교하고, MSCOCO 및 Effect 이미지를 활용한 인퍼런스 실험을 통해 모델의 성능을 분석
- 비교 모델별 인퍼런스 코드를 통합 및 정리하여 일관된 실험 환경을 구축

#### [View Project & Code.v1](https://github.com/ssoojeong/Style_Transfer_SOTA_Models_v1.git), [View Project & Code.v2](https://github.com/ssoojeong/Style_Transfer_SOTA_Models_v2.git)

---

### 📌 진행 현황
1. &#x2705; Style Transfer 비교 모델 조사
2. &#x1F680; 인퍼런스 실험 진행
    - &#x2705; (완료) 실험 진행: MSCOCO 2014 이미지 인퍼런스 테스트
    - &#x2705; (완료) 비교 모델 5개 - 인퍼런스용 코드 정리
    - &#x2705; (완료) 비교 모델 2개 추가 - 인퍼런스용 코드 정리
    - &#x2705; (완료) 실험 진행: Effeect 이미지 인퍼런스 테스트
    - &#x1F525; (예정) 비교 모델 5개 더 추가
    - &#x1F525; (예정) 환경 구축: Docker 생성
    - &#x1F525; (예정) 실험 진행: Effeect 이미지 인퍼런스 전수 완료

----

### &#x1F31F; Style Transfer 모델 리스트
<table border="1" cellspacing="0" cellpadding="8">
  <thead>
    <tr>
      <th>모델명</th>
      <th>학술대회/저널</th>
      <th>연도</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>DreamStyler</td>
      <td>AAAI</td>
      <td>2024</td>
    </tr>
    <tr>
      <td>ArtBank</td>
      <td>AAAI</td>
      <td>2024</td>
    </tr>
    <tr>
      <td>Zero</td>
      <td>CVPR</td>
      <td>2024</td>
    </tr>
    <tr>
      <td>StyleID</td>
      <td>CVPR</td>
      <td>2024</td>
    </tr>
    <tr>
      <td>ProSpect</td>
      <td>SIGGRAPH Asia</td>
      <td>2023</td>
    </tr>
    <tr>
      <td>VCT</td>
      <td>ICCV</td>
      <td>2023</td>
    </tr>
    <tr>
      <td>RIVAL</td>
      <td>NeurIPS</td>
      <td>2023</td>
    </tr>
    <tr>
      <td>DiffuseIT</td>
      <td>ICLR</td>
      <td>2023</td>
    </tr>
    <tr>
      <td>InST</td>
      <td>CVPR</td>
      <td>2023</td>
    </tr>
    <tr>
      <td>StyTR2</td>
      <td>CVPR</td>
      <td>2022</td>
    </tr>
    <tr>
      <td>IP-Adapter</td>
      <td>arXiv</td>
      <td>2023</td>
    </tr>
  </tbody>
</table>

----

## &#x1F60E; 인퍼런스 실험 수행 Guide

### 1. Dataset & Resources Download
- [dataset](https://1drv.ms/f/s!AunTciSw__3qjcswSBomygf2Ebo8AA?e=KkiNYO), [resources](https://1drv.ms/f/s!AunTciSw__3qjc991GMpiprnGnFhew?e=5fRIqo): OneDrive '소정' 폴더에서 다운로드
- 아래 경로에 dataset, resources 업로드

```bash
./{git clone directory}/dataset

./{git clone directory}/resources
```

---

### 2. Conda 환경 생성
```bash
conda env create -f environment.yaml

conda activate ldm
```
<p><strong>Note:</strong> 모델별로 conda 환경이 달라야 되서 실행 안될 수도 있음, 추후 도커 환경 구축 예정</p>

---

### 3. Inference 실행
```bash
python inference.py --model {model_name}
```
<p><strong>model_name:</strong> IP-Adapter, RIVAL, StyleID, StyTR2, VCT</p>

---

### 4. Output 확인
아래 폴더에 stylized image 생성

```bash
./stylized_images/{model_name}/style_{style_name}/content_{content_name}/*.png 
```

---

## Comparison Results
<img src="{{ site.baseurl }}/images/sota/comparison.png" alt="comparison" class="responsive-image">

- Qualitative comparisons of state-of-the-art diffusion models with zoomed-in views of stylized images on the MS-COCO 2017 dataset with four types of reference images from Wikiart.

<img src="{{ site.baseurl }}/images/sota/comparison2.png" alt="comparison2" class="responsive-image">

- Qualitative comparisons of state-of-the-art diffusion models on the FFHQ dataset with four types of reference images from Wikiart.


----

## To do List
- &#x1F525; (예정) 비교 모델 5개 더 추가
- &#x1F525; (예정) 환경 구축: Docker 생성
- &#x1F525; (예정) 실험 진행: Effeect 이미지 인퍼런스 전수 완료


