[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/3DbKuh4a)

# Document Type Classification | 문서 타입 분류

## Team CV 4조

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

- February 5, 2024 - Start Date
- February 19, 2024 - Final submission deadline

## 2. Components

### Directory

```
├── README.md
├── changhee
│   ├──DTC.ipynb
│   ├──DTC10.ipynb
│   ├──DTC11.ipynb
│   ├──DTC12.ipynb
│   ├──DTC13.ipynb
│   ├──DTC14.ipynb
│   ├──DTC15.ipynb
│   ├──DTC16.ipynb
│   ├──DTC17.ipynb
│   ├──DTC18.ipynb
│   ├──DTC19.ipynb
│   ├──DTC2.ipynb
│   ├──DTC20.ipynb
│   ├──DTC2_mixup.ipynb
│   ├──DTC3.ipynb
│   ├──DTC4.ipynb
│   ├──DTC5.ipynb
│   ├──DTC6.ipynb
│   ├──DTC7.ipynb
│   ├──DTC8.ipynb
│   ├──DTC9.ipynb
│   ├──aug_data1.ipynb
│   ├──aug_data2.ipynb
│   ├──aug_data2A.ipynb
│   ├──aug_data3.ipynb
│   ├──aug_data4.ipynb
│   ├──aug_data5.ipynb
│   └── eda.ipynb
├── hayeon
│   ├── Denoising.ipynb
│   ├── EDA.ipynb
│   ├── HybridEfficientNetSwinTransformer.ipynb
│   ├── efficientnetb0.ipynb
│   ├── efficientnetb1.ipynb
│   └── efficientnetb2.ipynb
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
    ├── offline_augmentation.ipynb
    ├── eda_code.ipynb
    ├── custom_efficientnetb4.ipynb
    └── 3_7_14_classifier.ipynb
```

## 3. Data descrption

### Dataset overview

- **(훈련 데이터셋)** 운전면허증, 진료확인서, 이력서, 차량 번호판 등 총 17종의 1570장의 문서 이미지
- **(테스트 데이터셋)** 훈련 데이터셋과 동일하게 17종의 문서 유형을 가진 3140장의 문서 이미지

### EDA

- 클래스 불균형
  
  - 0 ~ 16번까지의 클래스 중 1, 13, 14번의 클래스를 가진 이미지의 수가 타 클래스에 비해 적은 것을 확인
    
    <p align="center">
    <img src = "https://github.com/UpstageAILab/upstage-cv-classification-cv4/assets/73140315/b611985a-1451-47b7-9008-4468574788b0" width="60%" height="60%">
    </p>

- 테스트셋에서의 이미지
  
  - 비교적 선명하고 정방향인 훈련 데이터셋과 달리 원본사진에서 회전, 좌우반전, 이동, 잉크번짐 등으로 변형된 사진들을 다수 확인할 수 있음.

- 이미지 크기
  
  - 학습 데이터
    
    - Width - Mean: 497.61 / STD: 79.35
    
    - Height - Mean: 538.17 / STD: 76.05
      
      <img src = "https://github.com/UpstageAILab/upstage-cv-classification-cv4/assets/73140315/5fcf1731-f2ad-401f-a62e-40a5a384071d" width="50%" height="50%">
  
  - 평가 데이터
    
    - Width - Mean: 517.09 / STD: 79.83
    
    - Height - Mean: 518.55 / STD: 79.79
    
    <img src = "https://github.com/UpstageAILab/upstage-cv-classification-cv4/assets/73140315/b6f9d3d9-b561-415e-bce2-f3192134f5cb" width="50%" height="50%">

### Data Processing

1) 학습 데이터에서 잘못 레이블 되어 있는 데이터를 찾아 수정

2) Augmentation
   
   - 주어진 학습 데이터의 수(1,570장)가 평가 데이터(3,140장)의 수보다 적고, 정방향의 선명한 학습 데이터와 다르게 평가 데이터는 많이 변형되어 있기 때문에 다양한 augmentation 기법을 활용하여 이를 보완하였음
   
   - 학습 시간 단축을 위해 augmentation을 거친 이미지를 저장하여 사용하는 offline 방식으로 증강
   
   - **Albumentation**: Albumentation 라이브러리에서 **Transpose**, **ToGray**, **HorizontalFlip**, **Blur**,**GaussianNoise**, **ShiftScaleRotation** 등을 활용하여 훈련데이터를 변형하고 데이터의 수를 증강
   
   - **Augraphy**: Augraphy 라이브러리에서는 **PatternGenerator**, **BrightnessTexturize**와 **InkBleed** 방식을 활용하여 훈련데이터를 변형하고 데이터 수를 증강

3) 클래스 불균형을 oversampling을 통해 보완

## 4. Modeling

### Model descrition

- **이소영**
  - resnet50, resnext50, efficientnet_b0, efficientnet_b4 pre-trained 모델로 실험
    - 성능이 가장 좋았던 efficientnet_b4으로 고정
- **강승현**
  - timm : resnet34, resnet50, wide_resnet101_2, efficientnet_b0
  - huggingface transformers : [dit-large-finetuned-rvlcdip](https://huggingface.co/microsoft/dit-large-finetuned-rvlcdip)
    - 학습 시간과 리더보드 결과를 고려했을 때 efficientnet_b0 최종 선택
- **김하연**
  - Hybrid EfficientNet Swin-Transformer, efficientnet_b0, efficientnet_b1, efficientnet_b2
- **김창희**
  - resnet_34, deit_base_patch16_224, vit, efficientnet_b0, efficientnet_b4 중 efficientnet_b4가 가장 성능이 좋아 선택
### Modeling Process

- **이소영**
  - 이미지 전처리 시 Resize 대신 문서의 가로 세로 비율이 유지되도록 Padding 적용 -> 성능 향상
  
  - 예측 결과를 시각화하여 양식이 유사한 3, 7, 14 클래스에 대한 예측 성능이 떨어진다는 것을 확인
    
    - 3, 7, 14 클래스에 대한 샘플링 가중치를 증가시킴 -> 성능 향상
    - 3, 7, 14 클래스 별도 학습
      - efficientnet_b5 pre-trained 모델로 해당 클래스만 따로 학습하여 기존 결과값 대체 -> 스코어 향상
  
  - Test-Time Augmentation 적용
    
    - nference 단계에서 평가 이미지에 Flip(반전), RandomRotate(90도 단위 랜덤 회전)을 적용해 online 방식으로 augmentation하여 N회 예측 수행
      - 20회 inference 후 soft-voting 앙상블 -> 스코어 향상
  - 리더보드 기준 최상위 예측값들을 hard-voting으로 앙상블
      -> 최종 리더보드 Public 스코어 0.9631 달성
  
- **강승현**
  - 데이터 분할
    - K-Fold Cross-Validation 후 voting
    - 8 : 2 , 9 : 1 random split
      - 최종 선택 :  K-Fold Cross-Validation 후 voting
  - 학습률(LR) : 0.001 ~ 0.005
    - 최종 선택 : 0.001
  - Earlystopping 적용(patience : 2 ~ 5)
    - 최종 선택 : 5
  - 손실 함수는 Cross-Entropy Loss 최적화 알고리즘은 Adam 사용

    -> 최종 리더보드 Public 스코어 0.9397 달성
    
- **김하연**
 - Hybrid EfficientNet Swin-Transformer  <br>
<img src="https://github.com/UpstageAILab/upstage-cv-classification-cv4/assets/106041730/8fb4f1df-5075-4502-9355-39d96d379104" alt="Hybrid EfficientNet Swin-Transformer" width="300"/> <br>
    - ImageNet이 사전학습된 EfficientNet 인코더와 swin transformer block을 활용하는 Hybrid Swin Transformer 사용
    - Train Accuracy: 0.8893, Train F1 Score: 0.8546, Validation Accuracy: 0.8604, Validation F1 Score: 0.8224
      
  - EfficientNet Ensemble
    | ![EfficientNet-B0](https://github.com/UpstageAILab/upstage-cv-classification-cv4/assets/106041730/1f46a7ef-4cfa-4200-9493-fe99fc56cb38) | ![EfficientNet-B1](https://github.com/UpstageAILab/upstage-cv-classification-cv4/assets/106041730/5b1c1d9e-42e8-4c1b-938d-0bf7c9d3aac7) | ![EfficientNet-B2](https://github.com/UpstageAILab/upstage-cv-classification-cv4/assets/106041730/da3e5e60-b831-47de-8c6a-61d481fb5e2d) |
    |:---:|:---:|:---:|
    | EfficientNet-B0 | EfficientNet-B1 | EfficientNet-B2 |

    - EfficientNet B0, B1, B2는 모델 크기와 input image resolution에서 차이가 있으며 B0가 가장 작은 크기를 가지고 B2가 상대적으로 큰 크기를 가짐
    - 각 모델을 K-Fold 진행
    - 세 모델 결과값 hard voting ensemble하여 최종 제출 결과 f1 score 0.9384
- **김창희**
    - 3, 4, 7, 14 번에 예측 성능이 떨어지는 것을 확인 
    	- 3, 4, 7, 14번에 클래스 가중치 적용
    	- 3, 4, 7, 14번 데이터 추가적인 증강 
    - fine-tuning에서 lr과 batch_size에는 양의 상관관계가 있다는 것을 확인 
    	- 최적의 조합인 batch_size : 16, lr : 1e-4 사용 
    - 최종적으로 상위 3개의 예측값들을 hard-voting으로 앙상블 -> public f1 score 0.9560

## 5. Result

### Leader Board

- **Leader Board**

<p align="center">
<img src = "https://github.com/UpstageAILab/upstage-cv-classification-cv4/assets/73140315/0c56a1d8-82bc-4e1a-be3f-1825eaacc3dc" width="90%" height="90%">
</p>

- **F1 Score**: 0.9547

### Presentation

- https://docs.google.com/presentation/d/1iv7GAZ4cH0iCpFHj8IhVVAvt-fD_SzIziVl9zdpGBP8/edit#slide=id.g2ba9187747f_0_128
- [PDF](https://github.com/UpstageAILab/upstage-cv-classification-cv4/blob/a59d60165f1eb8c928c105701c66ad7966ce5fd5/%5B%E1%84%91%E1%85%A2%E1%84%89%E1%85%B3%E1%84%90%E1%85%B3%E1%84%8F%E1%85%A2%E1%86%B7%E1%84%91%E1%85%A5%E1%84%89%E1%85%B3%5D%20Upstage%20AI%20Lab%201%E1%84%80%E1%85%B5_4%E1%84%8C%E1%85%A9_%E1%84%80%E1%85%A7%E1%86%BC%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%83%E1%85%A2%E1%84%92%E1%85%AC%20%E1%84%87%E1%85%A1%E1%86%AF%E1%84%91%E1%85%AD%E1%84%8C%E1%85%A1%E1%84%85%E1%85%AD.pdf)

## 6. etc

### Meeting Log

- https://quickest-asterisk-75d.notion.site/d7375c36ef604a78aefb28206824c8f4?v=62365b42756244cf82f399cc24ed5bf0

### Reference

- _Insert related reference_
