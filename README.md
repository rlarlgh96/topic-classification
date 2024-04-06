# Topic Classification(TC)

## 프로젝트 개요
### 대회 소개
<img width="750" src="https://github.com/rlarlgh96/topic-classification/assets/121072239/72d89c2b-c611-4e38-8de6-ea8007210cfb"><br>
- 본 프로젝트는 네이버 부스트캠프 AI Tech 6기 NLP 트랙 과정에서 진행한 교육용 대회 프로젝트이다.
- Topic Classification(TC)는 뉴스의 헤드라인을 통해 그 뉴스가 어떤 topic을 갖는지를 분류해내는 task로, 본 대회는 baseline 코드를 수정하지 않고 데이터만을 가지고 모델 성능 향상을 이끌어내는 Data Centric 대회이다.

### 평가 방법
- 본 대회에서는 macro F1 score을 평가 지표로 사용한다.

## 프로젝트 수행 과정
### Data augmentation
<img width="750" src="https://github.com/rlarlgh96/topic-classification/assets/121072239/bca34b87-2886-4f39-b9a9-60bab33596f0"><br>
- ***Conditional BERT Contextual Augmentation*** 논문에서는 BERT MLM 모델에 label embedding을 추가하여, label을 고려한 마스킹된 토큰 예측을 통해 새로운 데이터 증강 방식을 제안한다.
- 이러한 방식을 적용하기 위해 논문에서 사용된 코드를 가져와 본 대회 task에 사용할 수 있도록 수정하였다.
- BERT MLM 모델을 fine-tuning한 다음, 학습한 모델로 train 데이터와 유사한 데이터를 만들어 데이터 증강을 시도하였다.
- 증강한 데이터의 결과는 다음과 같다.

  <img width="750" alt="320188463-cdc7637b-aadd-463e-a39f-52d02c293369" src="https://github.com/rlarlgh96/topic-classification/assets/121072239/d499719d-79fd-47f3-9b47-b5d4b98ba980"><br>

## 프로젝트 수행 결과
- 프로젝트 수행 결과, 모델의 성능을 0.0043점 향상시켰다.

  | model | score |
  |--------|--------|
  | Baseline | 0.8366 |
  | Data Augmentation | 0.8409 |


## 참고 문헌
- Wu, X., Lv, S., Zang, L., Han, J., & Hu, S. (2018). ***Conditional BERT Contextual Augmentation***. arXiv:1812.06705v1 [cs.CL].
