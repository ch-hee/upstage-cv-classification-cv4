[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/3DbKuh4a)

# Title (Please modify the title)

## Team

| ![박패캠](https://avatars.githubusercontent.com/u/156163982?v=4) | ![이패캠](https://avatars.githubusercontent.com/u/156163982?v=4) | ![최패캠](https://avatars.githubusercontent.com/u/156163982?v=4) | ![김패캠](https://avatars.githubusercontent.com/u/156163982?v=4) | ![오패캠](https://avatars.githubusercontent.com/u/156163982?v=4) | ![오패캠](https://avatars.githubusercontent.com/u/156163982?v=4) |
|:-------------------------------------------------------------:|:-------------------------------------------------------------:|:-------------------------------------------------------------:|:-------------------------------------------------------------:|:-------------------------------------------------------------:|:-------------------------------------------------------------:|
| [강승현](https://github.com/UpstageAILab)                        | [김형수](https://github.com/UpstageAILab)                        | [이소영A](https://github.com/UpstageAILab)                       | [김창희](https://github.com/UpstageAILab)                        | [진성준](https://github.com/UpstageAILab)                        | [김하연](https://github.com/UpstageAILab)                        |
| 팀장, 담당 역할                                                     | 담당 역할                                                         | 담당 역할                                                         | 담당 역할                                                         | 담당 역할                                                         | 담당 역할                                                         |

## 0. Overview

### Environment

- **(컴퓨팅 환경)** 인당 RTX 3090 서버를 VSCode와 SSH로 연결하여 사용
- **(협업 환경)** Github, Wandb
- **(의사 소통)** Slack, Zoom

## 1. Competiton Info

### Overview

- computer vision domain에서 이미지 분류를 위한 대회로, 주어진 문서의 이미지를 해당 문서 유형으로 분류하는 대회

### Timeline

- ex) February 5, 2024 - Start Date
- ex) February 19, 2024 - Final submission deadline

## 2. Components

### Directory

```
├── README.md
├── changhee
│   ├── DTC.ipynb
│   ├── aug_data1.ipynb
│   └── aug_data2.ipynb
├── hayeon
│   └── EDA.ipynb
├── hyeongsoo
│   ├── augmentation_1.ipynb
│   ├── augmentation_2.ipynb
│   ├── augmentation_3.ipynb
│   ├── augmentation_4.ipynb
│   ├── augmentation_5.ipynb
│   ├── eda_1.ipynb
│   ├── eda_2.ipynb
│   └── eda_3.ipynb
├── seongjun
│   ├── 02.ipynb
│   ├── 04.ipynb
│   └── EDA01.ipynb
├── seunghyun
│   ├── augment.ipynb
│   ├── augmentation.ipynb
│   ├── augmentation_240213.ipynb
│   └── model_240215.ipynb
└── soyoung
    ├── code_0207.ipynb
    ├── eda_code.ipynb
    └── offline_aug_f.ipynb
```

## 3. Data descrption

### Dataset overview

- **(훈련 데이터셋)** 운전면허증, 진료확인서, 이력서, 차량 번호판 등 총 17종의 1570장의 문서 이미지
- **(테스트 데이터셋)** 훈련 데이터셋과 동일하게 17종의 문서 유형을 가진 3140장의 문서 이미지

### EDA

- 클래스 불균형
  - 0 ~ 16번까지의 클래스 중 1, 13, 14번의 클래스를 가진 이미지의 수가 타 클래스에 비해 적은 것을 확인
<p align="center">
<img src = "https://github.com/UpstageAILab/upstage-cv-classification-cv4/assets/73140315/b611985a-1451-47b7-9008-4468574788b0" width="40%" height="40%">
</p>

### Data Processing

- _Describe data processing process (e.g. Data Labeling, Data Cleaning..)_

## 4. Modeling

### Model descrition

- _Write model information and why your select this model_

### Modeling Process

- _Write model train and test process with capture_

## 5. Result

### Leader Board

- _Insert Leader Board Capture_
- _Write rank and score_

### Presentation

- _Insert your presentaion file(pdf) link_

## etc

### Meeting Log

- _Insert your meeting log link like Notion or Google Docs_

### Reference

- _Insert related reference_
