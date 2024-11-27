---
layout: post
title:  "Diffusion-based Text-to-Image Generations"
date:   2023-05-31 18:05:55 +0300 
image:  diffusion/1.png
tags:   Study
---

## &#x1F4E2; Project Overview: 2303~2306

<img src="{{ site.baseurl }}/images/diffusion/1.png" alt="samples" class="responsive-image">

### 주요 기능
- 텍스트 기반 이미지 생성 기능 제공
- Diffusion T2I 모델 성능 비교
- 다양한 평가 지표(e.g., IS, FID ...) 활용
- 통합된 가상 환경에서 간편한 설치 및 실행

### [View Project & Code](https://github.com/ssoojeong/Diffusion-based_Text-to-Image_Generation.git)

----

### &#x1F31F; Diffusion T2I 모델 리스트
- GLIDE (Classifier Guidance)
- GLIDE (Classifier Free Guidance)
- VQ-Diffusion
- Stable Diffusion

---

### &#x1F4AB; 성능 평가 지표 리스트
- Inception score (IS): 이미지 품질, 다양성
- Fréchet Inception Distance (FID): 이미지 간의 유사성
- CLIP Text Similarity Score (CLIP score): 텍스트와 이미지 간의 의미적 일치도
- Peak Signal-to-Noise Ratio (PSNR): 이미지의 재현 성능
- Structural Similarity Index Measure (SSIM): 이미지 간 구조적 유사성

----

### 💻 실험 방법
#### 1. 가상 환경 설정

```bash
conda create -n diffusion python=3.9
conda activate diffusion

pip install -r requirements.txt
pip install -e .
```
<p><strong>Note:</strong> GPU 사용 가능 환경에서 실행 권장</p>

---

#### 2. 텍스트 데이터 생성

```bash
python ./data/text_preprocessing.py
```

---

#### 3. 모델 실행

```bash
# 1. GLIDE
python ./model/glide.py --gpus 0

# 2. VQ-Diffusion
python ./model/vq_diffusion.py --gpus 0

# 3. Stable Diffusion
python ./model/stable_diffusion.py --gpus 0
```
<p><strong>이미지 저장 경로:</strong> ```./data_gen/{모델명}/image/```</p>

---

#### 4. 평가 지표 실행 - 성능 비교
```bash
# 1. IS, FID 실행
python ./metric/is_fid.py --model {모델명} --gpus 0

# 2. CLIPScore 실행
python ./metric/clipscore.py --model {모델명} --gpus 0

# 3. PSNR, SSIM 실행
python ./metric/psnr_ssim.py --model {모델명} --gpus 0
```
<p><strong>모델명:</strong> glide, vq, stable</p>

<p><strong>Glide 모델 추가 옵션:</strong> --classifier</p>

----

### 📄 논문 투고 및 게재 (2023 하계 전자공학회)
A study of text guided image generation based on diffusion model 
[[paper]](https://drive.google.com/file/d/1HEqo99ew1ocv_f1DmFJf5eplb3pd8zUl/view?usp=sharing) 

(확산 모델 기반 텍스트 정보를 이용한 이미지 생성 모델 연구)

<img src="{{ site.baseurl }}/images/diffusion/2.png" alt="Quantitative Results of MSCOCO 2014" class="responsive-image">