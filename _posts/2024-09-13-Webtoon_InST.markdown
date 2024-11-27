---
layout: post
title:  "Webtoon_InST"
date:   2024-09-13 18:05:55 +0300
image:  webtoon/demo.jpg
tags:   Project
---

## Preview of the Demo
<img src="{{ site.baseurl }}/images/webtoon/demo.jpg" alt="demo preview" class="responsive-image">

---

<!-- Image-to-Image Translation 데모 영상 -->
<div class="video-container">
    <h3>Image-to-Image Translation 데모 영상</h3>
    <iframe src="https://www.youtube.com/embed/4-QMtaXoLyc" allowfullscreen></iframe>
</div>

<!-- Text-to-Image Generation 안내 영상 -->
<div class="video-container">
    <h3>Text-to-Image Generation 안내 영상</h3>
    <iframe src="https://www.youtube.com/embed/pdjXOimKhbk" allowfullscreen></iframe>
</div>

<!-- Text-to-Image Generation 데모 영상 -->
<div class="video-container">
    <h3>Text-to-Image Generation 데모 영상</h3>
    <iframe src="https://www.youtube.com/embed/GM8euTbBVh8" allowfullscreen></iframe>
</div>

### [View Project & Code](https://github.com/ssoojeong/Webtoon_InST.git)

---

## Getting Started

We recommend running our code using:

- NVIDIA GPU + CUDA, CuDNN
- Python 3, Anaconda

<p align="right">(<a href="#top">back to top</a>)</p>

---

### 1. Installation

Clone the repositories.
   ```sh
   git clone https://github.com/ssoojeong/Webtoon_InST.git
   git clone https://github.com/zyxElsa/InST.git
   ```

<p><br></p> <!-- 줄바꿈 추가 -->

Run following commands to install necessary packages.
  ```sh
  conda env create -f environment.yaml
  conda activate ldm
  ```
<p align="right">(<a href="#top">back to top</a>)</p>

---

### 2. Pretrained Models for Webtoon_InST Inference
Download the pretrained models and save it to the indicated location.
<table border="1" cellspacing="0" cellpadding="8">
  <thead>
    <tr>
      <th>Pretrained Model</th>
      <th>Save Location</th>
      <th>Reference Repo/Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://huggingface.co/CompVis/stable-diffusion-v-1-4-original/resolve/main/sd-v1-4.ckpt" target="_blank">Stable Diffusion</a></td>
      <td>./InST/models/sd/sd-v1-4.ckpt</td>
      <td><a href="https://github.com/CompVis/stable-diffusion.git" target="_blank">CompVis/stable-diffusion</a></td>
    </tr>
    <tr>
      <td><a href="https://drive.google.com/drive/folders/1x0XIFSX6cKO3bjdaI3JOdUtLppqf9Qmy?usp=sharing" target="_blank">YeosinGangrim</a></td>
      <td>./InST/logs/yeosin/</td>
      <td><a href="https://comic.naver.com/webtoon/list?titleId=703846" target="_blank">여신강림-네이버웹툰</a></td>
    </tr>
    <tr>
      <td><a href="https://drive.google.com/drive/folders/1IQzcxdi8F2nAQaiZwtPyEqimt_UaZtH9?usp=sharing" target="_blank">UglyPeoples</a></td>
      <td>./InST/logs/ugly/</td>
      <td><a href="https://comic.naver.com/webtoon/list?titleId=732953" target="_blank">어글리피플즈-네이버웹툰</a></td>
    </tr>
    <tr>
      <td><a href="https://drive.google.com/drive/folders/1CI4e3Px_AC1ZIJokTtkF1wrjq2jYkVp4?usp=sharing" target="_blank">YumiSepo</a></td>
      <td>./InST/logs/yumi/</td>
      <td><a href="https://series.naver.com/comic/detail.series?productNo=3900477" target="_blank">유미의세포-네이버웹툰</a></td>
    </tr>
    <tr>
      <td><a href="https://drive.google.com/drive/folders/141l8dvD_tR7z2uqqnPwiPUht4Gukcge0?usp=sharing" target="_blank">Other style</a></td>
      <td>./InST/logs/etc/</td>
      <td><a href="https://arxiv.org/abs/2211.13203" target="_blank">An Image in the InST (CVPR, 2023) paper</a></td>
    </tr>
  </tbody>
</table>

<p align="right">(<a href="#top">back to top</a>)</p>

---

### 3. Implementation
Run following commands and open the shared link.
  ```sh
  python demo_canny.py
  ```
- The Gradio app allows you to change hyperparameters(steps, style guindace sclae, etc.)
- The [FFHQ](https://github.com/NVlabs/ffhq-dataset.git) sample datasets has been uploaded in the `./data/face`, so you can use it for testing.
<p align="right">(<a href="#top">back to top</a>)</p>

---

### 4. Results
- After translating an image with the gradio app, you can check the generated foler, `./demo_output`.
- Inside this folder, you'll find subfolders like `./demo_output/yeosin`, `./demo_output/ugly`, `./demo_output/love`, `./demo_output/etc`, each containing images transformed into their respective webtoon styles.
<p align="right">(<a href="#top">back to top</a>)</p>

<p><br></p> <!-- 줄바꿈 추가 -->

### 🎨 Image Samples
<img src="{{ site.baseurl }}/images/webtoon/samples.png" alt="sample images" class="responsive-image">

<p><br></p> <!-- 줄바꿈 추가 -->

### cf. Different style guidance scales for background and foreground
If you want to give different style guidance to the background and foreground, clone the repository below and use it.
  ```sh
  git clone https://github.com/xuebinqin/DIS.git
  ```
The Implementation code is already in this inference python file, but the detailed implementation method will be updated later.
<p align="right">(<a href="#top">back to top</a>)</p>

---

## Additional Experiments and Reports 
### Preview of [Report](https://drive.google.com/file/d/1DgdzqSxqderb0EcZexxKtg03py7JlrFS/view?usp=sharing)

<img src="{{ site.baseurl }}/images/webtoon/results.png" alt="results" class="responsive-image">

- In our experimentation with this proposed method, using Naver webtoon images as style images and FFHQ dataset images as content, we evaluated the performance of style transfer on human faces.

<p align="right">(<a href="#top">back to top</a>)</p>
