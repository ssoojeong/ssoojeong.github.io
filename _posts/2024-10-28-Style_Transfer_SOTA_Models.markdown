---
layout: post
title:  "Style Transfer SOTA Models"
date:   2024-10-28 18:05:55 +0300
image:  main.png
tags:   Study
---

## &#x1F4E2; Project Report Overview: 241028
1. &#x2705; Style Transfer 비교 모델 조사
2. &#x1F680; 인퍼런스 실험 진행
    - &#x2705; (완료) 실험 진행: MSCOCO 2014 이미지 인퍼런스 테스트
    - &#x1F525; (예정) 실험 진행: Effeect 이미지 인퍼런스 테스트
    - &#x1F525; (예정) 환경 구축: Docker 생성
    - &#x1F525; (예정) 실험 진행: Effeect 이미지 인퍼런스 완료

## 1. &#x2705; Style Transfer Comparison Models
### &#x1F31F; Recommended for use (Qualitative Results Good)
<table border="1">
  <thead>
    <tr>
      <th>Model Name</th>
      <th>Conference / Source</th>
      <th>Paper Title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://github.com/tencent-ailab/IP-Adapter.git"><b>IP-Adapter</b></a></td>
      <td>arXiv, 성능 좋음</td>
      <td>"IP-Adapter: Text Compatible Image Prompt Adapter for Text-to-Image Diffusion Models"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/HolmesShuan/Zero-shot-Style-Transfer-via-Attention-Rearrangement.git"><b>Zero</b></a></td>
      <td>CVPR 2024</td>
      <td>"Z∗: Zero-shot Style Transfer via Attention Rearrangement"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/dvlab-research/RIVAL.git"><b>RIVAL</b></a></td>
      <td>NeurIPS 2023</td>
      <td>"Real-World Image Variation by Aligning Diffusion Inversion Chain"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/diyiiyiii/StyTR-2.git"><b>StyTr2</b></a></td>
      <td>CVPR 2022</td>
      <td>"StyTr^2: Image Style Transfer with Transformers"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/jiwoogit/StyleID.git"><b>StyleID</b></a></td>
      <td>CVPR 2024</td>
      <td>"Style Injection in Diffusion: A Training-free Approach for Adapting Large-scale Diffusion Models for Style Transfer"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/cyclomon/DiffuseIT.git"><b>DiffuseIT</b></a></td>
      <td>ICLR 2023</td>
      <td>"Diffusion-based Image Translation using Disentangled Style and Content Representation"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/curryjung/InjectFusion_official.git"><b>InjectFusion</b></a></td>
      <td>arXiv</td>
      <td>"Training-free Content Injection using h-space in Diffusion models"</td>
    </tr>
  </tbody>
</table>

### &#x1F60E; Not recommended for use (참고용)
<table border="1">
  <thead>
    <tr>
      <th>Model Name</th>
      <th>Conference / Source</th>
      <th>Paper Title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://github.com/ssoojeong/Webtoon_InST.git"><b>Proposed Method</b></a></td>
      <td>InST 모델 베이스 제안 방법</td>
      <td>"InST 모델 베이스 제안 방법"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/zyxElsa/InST.git"><b>InST</b></a></td>
      <td>CVPR 2023</td>
      <td>"Inversion-Based Style Transfer with Diffusion Models"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/zyxElsa/ProSpect.git"><b>ProSpect</b></a></td>
      <td>SIGGRAPH Asia 2023</td>
      <td>"ProSpect: Prompt Spectrum for Attribute-Aware Personalization of Diffusion Models"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/CrystalNeuro/visual-concept-translator.git"><b>VCT</b></a></td>
      <td>ICCV 2023</td>
      <td>"General Image-to-Image Translation with One-Shot Image Guidance"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/webtoon/dreamstyler.git"><b>DreamStyler</b></a></td>
      <td>AAAI 2024</td>
      <td>"DreamStyler: Paint by Style Inversion with Text-to-Image Diffusion Models"</td>
    </tr>
    <tr>
      <td><a href="https://github.com/Jamie-Cheung/ArtBank.git"><b>ArtBank</b></a></td>
      <td>AAAI 2024</td>
      <td>"ArtBank: Artistic Style Transfer with Pre-trained Diffusion Model and Implicit Style Prompt Bank"</td>
    </tr>
  </tbody>
</table>


##### <span style="color:dodgerblue;">\*</span><span style="color:gray;">: _(style 1개) 인퍼런스 테스트 완료_</span>

##### <span style="color:dodgerblue;">\*</span><span style="color:dodgerblue;">\*</span><span style="color:gray;">: _(style 10개) 인퍼런스 테스트 완료_</span>



## 2. &#x1F680; Experimental Results

#### &#x2705; (완료) 실험 진행: MSCOCO 2014 이미지 인퍼런스 테스트
- [Stylized Images](https://1drv.ms/f/s!AunTciSw__3qjYUHcKZCyw9OaucVZQ?e=nUVnGF): OneDrive '소정' 폴더에 업로드
        
    ``` 
    소정
    └── 241027_Stylized_Images
        │
        ├── IP-Adapter
        │   ├── sg_0.4
        │   ├── sg_0.5
        │   └── sg_0.6
        │       ├── style_1
        │       │   ├── COCO_train2014_{idx}.png
        │       │   └── ...
        │       └── ...      
        │      
        ├── RIVAL
        │   ├── style_1
        │   │   ├── COCO_train2014_{idx}.png
        │   │   └── ...
        │   └── ...      
        │
        ├── StyleID
        ├── StyTr2 
        └── Zero
            
    ``` 

#### &#x1F525; (예정) 실험 진행: Effeect 이미지 인퍼런스 테스트

#### &#x1F525; (예정) 환경 구축: Docker 생성

#### &#x1F525; (예정) 실험 진행: Effeect 이미지 인퍼런스 완료

