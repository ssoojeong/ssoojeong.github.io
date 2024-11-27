---
layout: post
title:  "Style Transfer SOTA Models"
date:   2024-10-28 18:05:55 +0300
image:  main.png
tags:   Study
---

# 

## &#x1F4E2; Project Report Overview: 241028
1. &#x2705; Style Transfer 비교 모델 조사
2. &#x1F680; 인퍼런스 실험 진행
    - &#x2705; (완료) 실험 진행: MSCOCO 2014 이미지 인퍼런스 테스트
    - &#x1F525; (예정) 실험 진행: Effeect 이미지 인퍼런스 테스트
    - &#x1F525; (예정) 환경 구축: Docker 생성
    - &#x1F525; (예정) 실험 진행: Effeect 이미지 인퍼런스 완료

## 1. &#x2705; Style Transfer Comparison Models
### &#x1F31F; Recommended for use (Qualitative Results Good)

| Model Name   | Conference / Source   | Paper Title                                                                                                             |
|--------------|-----------------------|-------------------------------------------------------------------------------------------------------------------------------|
| [**IP-Adapter](https://github.com/tencent-ailab/IP-Adapter.git) | arXiv, 성능 좋음        | "IP-Adapter: Text Compatible Image Prompt Adapter for Text-to-Image Diffusion Models"  |                                         |
| [**Zero](https://github.com/HolmesShuan/Zero-shot-Style-Transfer-via-Attention-Rearrangement.git) | CVPR 2024              | "Z∗: Zero-shot Style Transfer via Attention Rearrangement"                                                                     |
| [**RIVAL](https://github.com/dvlab-research/RIVAL.git)         | NeurIPS 2023           | "Real-World Image Variation by Aligning Diffusion Inversion Chain"                                                             |
| [*StyTr2](https://github.com/diyiiyiii/StyTR-2.git)             | CVPR 2022              | "StyTr^2: Image Style Transfer with Transformers"                                                                             |
| [*StyleID](https://github.com/jiwoogit/StyleID.git)             | CVPR 2024              | "Style Injection in Diffusion: A Training-free Approach for Adapting Large-scale Diffusion Models for Style Transfer"          |
| [DiffuseIT](https://github.com/cyclomon/DiffuseIT.git)           | ICLR 2023              | "Diffusion-based Image Translation using Disentangled Style and Content Representation"                                        |
| [InjectFusion](https://github.com/curryjung/InjectFusion_official.git) | arXiv                  | "Training-free Content Injection using h-space in Diffusion models"                                                           |


### &#x1F60E; Not recommended for use (참고용)
| Model Name   | Conference / Source   | Paper Title                                                                                                                   |
|--------------|-----------------------|-------------------------------------------------------------------------------------------------------------------------------|
| [**Proposed Method](https://github.com/ssoojeong/Webtoon_InST.git) | InST 모델 베이스 제안 방법        | "InST 모델 베이스 제안 방법"                                                                                                  |
| [**InST](https://github.com/zyxElsa/InST.git)           | CVPR 2023              | "Inversion-Based Style Transfer with Diffusion Models"                                                                         |
| [**ProSpect](https://github.com/zyxElsa/ProSpect.git)   | SIGGRAPH Asia 2023     | "ProSpect: Prompt Spectrum for Attribute-Aware Personalization of Diffusion Models"                                            |
| [**VCT](https://github.com/CrystalNeuro/visual-concept-translator.git) | ICCV 2023              | "General Image-to-Image Translation with One-Shot Image Guidance"                                                             |
| [**DreamStyler](https://github.com/webtoon/dreamstyler.git) | AAAI 2024              | "DreamStyler: Paint by Style Inversion with Text-to-Image Diffusion Models"                                                   |
| [**ArtBank](https://github.com/Jamie-Cheung/ArtBank.git) | AAAI 2024              | "ArtBank: Artistic Style Transfer with Pre-trained Diffusion Model and Implicit Style Prompt Bank"                             |

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

